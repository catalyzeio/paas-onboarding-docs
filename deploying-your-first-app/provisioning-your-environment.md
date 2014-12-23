# Provisioning your environment

> "As you wish." 

> — Westley, The Princess Bride

After you've sent us that email, you will shortly receive an email from us which looks something like this:

**TO BE UPDATED SHORTLY**


````
Welcome to Catalyze!

Thank you for setting up your environment on Catalyze. 

Per the data that you entered, we have provisioned the following containers:


- (x1) GB: {{HA}} - app containers
- (x2) GB: {{HA}} - {{image}} database containers
- (x3) GB - {{image}} cache container

Your git url to push code to is: {{customer_git_url}}

Please push the code to that git url. Note that the user pushing code to the environment must have an SSH key that has already been setup during the environment creation process.

Once the code has been pushed and you don't see any errors during the build process, you should be able to:

1. Access the app at the IP address provided above
2. Log back into the dashboard and get a quick view into your environment status
3. Click on the buttons provided to access your logging and monitoring instances. (Metrics is still in process and is a value add service we intend to provide shortly)

The IP address of your application is: {{customer_IP_addr}}

Your application is temporarily (until you set up your DNS) available at: {{customer_app_url}}

Please feel free to contact us on your dedicated slack channel or via email - support@catalyze.io with any questions or concerns or problems. 

Sincerely,

The Catalyze Team.

````


