# Architecting your app for Catalyze

> Good design is good business.

> — Thomas J. Watson

As discussed earlier, we've modeled our PaaS after Heroku. Heroku follows the principles of the [12-factor app](http://12factor.net/). This approach was written by Heroku co-founder Adam Wiggins, and is a methodology for building software-as-a-service apps in modern deployment environments.

Similar to [Heroku](https://devcenter.heroku.com/articles/architecting-apps#on-heroku), the core development principles on Catalyze differ from traditional server based hosting solutions in the following ways:

- it is application-, not infrastructure-, focused
- is a dynamic and distributed runtime environment
- utilizes a process-based execution model
- enforces a strict separation of apps and their dependencies

*Source: [Heroku Development Center](http://devcenter.heroku.com)*

The two key architectural change that needs to be put into place for any application to work on Catalyze are:

- Clear separation of code, configuration and dependencies and
- Applications must be runnable as independent, lightweight, and stateless processes with quick startup and shutdown.

### Separation of code, configuration and dependencies

#### Code
You are likely to have multiple versions of your app - development, staging and production. Since you will use some form of CVS, you should separate the codebases for each environment and deploy the appropriate version to the corresponding environment.

If your app is made up of multiple smaller apps, each of the smaller apps should be deployed as independent apps.

See [here](https://devcenter.heroku.com/articles/development-configuration#applications-codebases) for more details.

#### Configuration
Configuration parameters allow you to specify the type of environment (dev, qa, production etc.), database names, third party credentials etc. These should **not** be part of the code but rather provided and managed independently.

See[here](https://devcenter.heroku.com/articles/development-configuration#configuration) for more details.

#### Dependencies
Application dependencies, such as plugins and required third-party libraries should be explicitly declared and isolated.

See [here](https://devcenter.heroku.com/articles/development-configuration#dependencies) for more details.

### Stateless applications
Twelve-factor processes are stateless and share-nothing. Any data that needs to persist must be stored in a stateful backing service, typically a database. If the application is stateless (which it will be if the above three principles are implemented), then your application can be managed, deployed, backed up, restored without any complications and at speed.


