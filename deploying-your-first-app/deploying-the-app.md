---
title: Deploying the app
---

# Deploying the app

> Button, button, who's got the button?

> — Willy Wonka


At this point you'll switch over to the CLI. Be sure you've installed the CLI ([instructions here](https://github.com/catalyzeio/cli/blob/master/README.md)).

Using your terminal navigate to your application's code layer (i.e. if you're building a rails app you'll want to be in your root directory where `.git` is typically located). You need to associate your local repository with your Catalyze environment name

```
catalyze associate your_env_name
```

Replace *your_env_name* in the example above with the environment name that is in your dashboard. Now push your code to Catalyze.

```
$ git push catalyze master
```

**NOTE**: The very first time you push the code, we will manually do the deploy for you. This is needed to ensure that the connections have all been set up accurately and the containers are all wired up to the logging and monitoring interfaces. After the first deploy by us, any and all subsequent git pushes / deploys by you will be automatic and will not require any intervention from us.

Every time you do a git push (after the first time), you will see the build output scroll past on your terminal. If you see errors, please fix those and re-deploy. We are continually working on documenting some of the more common [issues and problems](https://resources.catalyze.io/paas/paas-faq/) that other customers have run into specific to the various combinations of languages and databases and the possible fixes or workarounds. That repo is also public and accessible [here](https://github.com/catalyzeio/paas-faq) so please also feel free to suggest edits / changes / topic suggestions etc.
