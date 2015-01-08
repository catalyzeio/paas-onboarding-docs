---
title: The PaaS CLI
---
# The PaaS CLI

> I can’t abide that contraption attached to the computer which must be gripped to navigate a cursor round a computer screen, a move which necessitates removing one’s hands from the keyboard and removing it to a misshapen blob, interrupting the flow of work.

>   — William M. Briggs

# Quickstart

## Installing
1. Extract the provided zip for your platform.
2. Move the extracted `catalyze` binary to a directory that's on your PATH (e.g. `/usr/bin`)
    * In the future, this will be replaced by an installer - this is just for the alpha release.

To verify: `catalyze --version`

## Associating a local repo with a provisioned environment

1. `cd` into the project directory (the one that contains the `.git` directory).
2. `catalyze associate <environment>`, substituting `<environent>` for the name of the environment you had provisioned.
    * This will ask you for a set of credentials. These are the same credentials you use on the dashboard.
    * Your environment name is listed in the dashboard. If you're not sure, run `catalyze environments`.
3. You should now have a git remote named `catalyze`. To verify: `git remote -v`

## Building/Deploying
1. Before deploying, a container needs to be built. To do this, push master to the catalyze remote (`git push catalyze master`).
2. After that succeeds, you're clear to deploy. `catalyze deploy`

## Environment Variables
* To check what's set: `catalyze vars`
* To set a variable: `catalyze vars set VARIABLE_NAME=value`
* To unset a variable: `catalyze vars delete VARIABLE_NAME`

Environment variable changes will get picked up when a deploy or redeploy occurs.

## Redeploying
Each successful new build from a push will redeploy the containers.

## Helpful commands
* `catalyze status` - Shows the status of your environment and each service.
* `catalyze dashboard` - Open the dashboard in your default browser.
* `catalyze help`
