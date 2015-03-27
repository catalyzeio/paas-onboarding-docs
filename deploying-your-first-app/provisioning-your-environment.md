---
title: Provisioning your environment
---

# Provisioning your environment

> "As you wish."

> — Westley, The Princess Bride

Once we've received your ticket, after you've selected the "Provision Environment" button, we will confirm your details and move forward with provisioning. You will receive an email with an update to the open support ticket outlining your environment details. Included will be links to your logging and monitoring server, as well as other information. Please see below for a template of the ticket update that you will receive:


<div class="r_md-panel">
Hi,

We have provisioned the new environment for you. Here are the details:

Public IP: {{ip_address}} The environment is setup for you to add a DNS record for the IP.

We have configured a temporary URL for you to use: {{temp_url}} e.g. https://podxxx.catalyze.io

Through the temporary URL, you will have access to a
- logging server: {{temp_url}}/logging/ 
- monitoring server: {{temp_url}}/monitoring/

To access these endpoints you will be prompted for a username and password. Enter your Dashboard credentials to gain access.

The endpoint connection information for the resources your application will consume is available in the environment variables for your environment.  You can view your environment variables in the Catalyze Dashboard or with the catalyze-paas-cli client program with the command:  `catalyze vars list`

You can download the CLI here - https://github.com/catalyzeio/catalyze-paas-cli. All associated install instructions are also available in the repo.

Lastly, the Git repo has been setup for your environment: {{git_url}}. 

You can add a remote and begin pushing to the master branch. The command to use would look like this - 
`git push catalyze yourbranch:master`

You need to replace “yourbranch” with the correct location and name of your repo. Once you have pushed code there and the build succeeds, send me a note and I will deploy the service. After the initial deploy, “git push” using the same command as above, will automatically redeploy the app.

Please let us know if you have any issues getting set up and going with your new environment. You can get our attention by emailing support@catalyze.io. 

Detailed onboarding documents and a getting started guide are available here - https://resources.catalyze.io/paas/getting-started

A FAQ on commonly asked questions is available here - https://resources.catalyze.io/paas/paas-faq

</div>