---
title: Deploying the app
---

# Deploying the app

> Button, button, who's got the button?

> — Willy Wonka

At this point, you will need to switch over to your terminal. Type the following into your terminal after you are in your code directory. Replace *your_env_name* in the example below with the environment name you specified [earlier](//resources.catalyze.io/paas/getting-started/deploying-your-first-app/environment-name/).

```
$ git remote add catalyze git@git.catalyze.io:your_env_name-code.git
$ git push catalyze master
```

You will see the build output scroll past on your terminal. If you see errors, please fix those and re-deploy. Coming soon is a list of problems that we've seen happen and possible fixes or workarounds.
