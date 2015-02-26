---
title: Updating your environment
---

# Updating your environment

> Change is inevitable. Change is constant.

>   — Benjamin Disraeli

Of course, as your application continues to evolve, you will find a need to add or change environment variables, and add or remove ssh keys, etc.

Once your environment has been provisioned, or saved, you will see it in the environment archive in the environments section of the dashboard (this is the initial screen you see when selecting your product after signing in - `dashboard.catalyze.io/environments`). To the left you will see a listing of your environments. Depending on the state of your environment you will see various links in the main environment panel. These correspond to:

- Overview (your environment's services and their associated information)
- Monitoring (health checks on your environment - Sensu)
- Logging (application logs - ELK Stack: Elastic Search, LogStash, Kibana)
- Update (update your saved environment's information)

####If the environment has not been provisioned yet
You will see an **Update** link in the bottom navigation area of the main environment panel.

![Update Environment](http://cdn2.dropmark.com/45280/232884f563d6d6ed1a458201faf96606b887feb7/db_update.png)

Click on the **Update** link to edit details about your environment. This is essentially and exact replica of the creation steps when you initially built your environment.

![Update Environment Details](http://cdn2.dropmark.com/45280/fd551d28b44e74e8217ef2dc8d50bb14a77c2be2/db_update-steps.png)

This will allow you to make changes to your existing environment prior to provisioning. If you make any changes, please be sure to let us know by [resending the email](./deploying_your_first_app/review_your_settings.html).

####If your environment has already been provisioned
You will see an **Overview** link in the bottom navigation area of the main environment panel.

![View Environment](http://cdn2.dropmark.com/45280/24d6a733ae8cce4671d79eb6e6b1be61525df4ac/db_overview.png)

Clicking on the **Overview** link will take you to the Overview screen as shown below. Note the edit button in the top right.

![View Environment Summary](http://cdn2.dropmark.com/45280/46e25d81e05a19dcbd441f900b11df65db19dd7c/db_overview-page.png)

Clicking on the **Edit** button allows you to *currently*, only edit:

1. **Environment Variables** and
2. **SSH keys**

as shown below.

![Edit Keys and Variables](http://cdn2.dropmark.com/45280/90f34736ef0eed5df37076d9125c98b6317007b8/db_edit.png)

We are currently developing the ability to allow users to edit and scale their environments in different ways.

**Note:** Any changes made to SSH Keys and Environment Variables will take hold after you next git push or deploy.