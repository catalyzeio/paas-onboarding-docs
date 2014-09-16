# Deploying your first app

> Coming together is a beginning; keeping together is progress; working together is success.

> — Henry Ford

To deploy your application, you will need to first register for an account on the dashboard. Usually this will be preceded by a couple of conversations with us to ensure that we jointly understand:
1. Whether we can support your requirements. Generally, if your solution is deployable on Heroku, it will work on the Catalyze PaaS. Custom buildpacks are also possible. You will need to get [in touch](support@catalyze.io) with us for that
2. Your overall architecture requirements - single node or highly available, database clustering requirements etc.
3. Your specific requirements around backup, disaster recovery, whether you need to store static content / assets and whether that need to be encrypted etc.
3. Pricing
4. The business associate agreement (BAA) and sign it




Info we need:
1. SSH public key for each user that requires git push access.

2. Domain Name, SSL certificate, SSL certificate key,  RootCA Certificate, and Intermediary Certificate.   Alternatively some vendors provide a bundled PEM file formatted for NGINX that includes all of the above.  In that case we would require only the PEM and KEY file.

3. Initial list of environment variables, and their values.
