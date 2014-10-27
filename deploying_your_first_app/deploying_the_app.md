# Deploying the app

> Button, button, whose got the button?

> — Willy Wonka

At this point, you will need to switch over to your terminal. Type the following into your terminal after you are in your code directory. Replace *your_env_name* in the example below with the environment name you specified [earlier](./environment_name.html).

```
$ git remote add catalyze git@git.catalyze.io:your_env_name-code.git
$ git push catalyze master
```

You will see the build output scroll past on your terminal. If you see errors, please fix those and re-deploy. Coming soon is a list of problems that we've seen happen and possible fixes or workarounds.
