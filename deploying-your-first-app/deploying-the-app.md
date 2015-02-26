---
title: Deploying the app
---

# Deploying the app

> Button, button, who's got the button?

> - Willy Wonka

At this point you'll switch over to the CLI. Using your terminal navigate to your application's code layer (i.e. if you're building a rails app you'll want to be in your root directory where `.git` is typically located). Replace *your_env_name* in the example below with the environment name you specified [earlier](//resources.catalyze.io/paas/getting-started/deploying-your-first-app/environment-name/).

```
$ git remote add catalyze git@git.catalyze.io:your_env_name-code.git
$ git push catalyze master
```

You will see the build output scroll past on your terminal. If you see errors, please fix those and re-deploy. We are currently working on a list of problems that we've seen happen and possible fixes or workarounds.