---
title: Updating your environment
---
# Updating your environment

> Change is inevitable. Change is constant.

>   — Benjamin Disraeli

Of course, as you continue to evolve your application, you will find a need to add or change environment variables, add or remove ssh keys etc. 

After your environment has been provisioned, you will see the listing of your environments as soon as you login. You will see a listing on the left nav and a summary listing of the state of the environments and the associatd logging / monitoring, details and other links on the main panel as shown below. 

####If the environment has not been provisioned yet
You will see an **Update** link next to the name of your environment on the main panel as shown below.

![Update Environment](/assets/img/pics/38.update.env.png)

Click on the **Update** link and you will be taken to editable set of screens of your enviroment as shown below 

![Update Environment Details](/assets/img/pics/39.update.env.details.png)

This will allow you to make changes to your existing environment prior to provisioning. If you make any changes, please be sure to let us know by [resending the email](./deploying_your_first_app/review_your_settings.html).

####If your environment has already been provisioned
You will see a **View** link next to the name of your environment on the main panel as shown below. 

![View Environment](/assets/img/pics/40.view.env.png)

Clicking on the **View** link will take you to the Overview screen as shown below. Note the large green **Edit** button

![View Environment Summary](/assets/img/pics/41.view.overview.png)

Clicking on the **Edit** button allows you to *currently*, only edit 

1. **Environment Variables** and 
2. **SSH keys**

as shown below.

![Edit Keys and Variables](/assets/img/pics/42.edit.keys.vars.png)


The functionality and supporting APIs to support editing and updating all the other aspects of your environment is in progress and under development.


Any updates that you make to the enviroment variables or SSH keys will be picked up the next time you do a git push or deploy.

