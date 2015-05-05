---
title: The PaaS CLI
---
# The PaaS CLI

> I can't abide that contraption attached to the computer which must be gripped to navigate a cursor round a computer screen, a move which necessitates removing one's hands from the keyboard and removing it to a misshapen blob, interrupting the flow of work.

> — William M. Briggs

# Quick Start
To use the CLI, it is assumed that you've already got an environment provisioned and set up a contract with Catalyze. If you have not yet done this, you can sign up and get started [here](https://catalyze.io/signup/paas).

## Installing
Follow the instructions at [https://github.com/catalyzeio/catalyze-paas-cli](https://github.com/catalyzeio/catalyze-paas-cli).

More details and the sets of commands supported are available [here](https://resources.catalyze.io/paas/cli/). The repo linked above is also open source so feel free to issue a pull request, suggest improvemennts or create issues as you use it.

<!--## Associating a local repository with a provisioned environment

1. `cd` into the project directory (the one that contains the `.git` directory).
2. `catalyze associate <environment>`, substituting `<environment>` for the name of the environment you had provisioned.
    * This will ask you for a set of credentials. These are the same credentials you use on the dashboard.
    * Your environment name is listed in the dashboard. If you're not sure, run `catalyze environments` - this will list all environments to which you have access.
3. You should now have a git remote named `catalyze`. To verify: `git remote -v`

## Building/Deploying
To deploy, simply push `master` to the `catalyze` remote (`git push catalyze master`).

## Environment Variables
* To check what's set: `catalyze vars`
* To set a variable: `catalyze vars set VARIABLE_NAME=value [VARIABLE_NAME_2=value2 ...]`
* To unset a variable: `catalyze vars delete VARIABLE_NAME`

Environment variable changes will get picked up when a deploy or redeploy occurs.

## Redeploying
Each successful new build from a push will restart that container. If you'd like to redeploy without a push (to pick up environment variable changes, for example), use `catalyze redeploy`.

## Helpful commands
* `catalyze status` - Shows the status of your environment and each service.
* `catalyze dashboard` - Open the dashboard in your default browser.

Run `catalyze --help` for the full list. To get help on an individual command, run `catalyze <command> --help`. -->
