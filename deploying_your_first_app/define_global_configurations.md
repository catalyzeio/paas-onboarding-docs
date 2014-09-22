# Define configurations

> Coding is long. Design is short. Paper is cheap.

> — Anonymous

The key data elements that need to be specified are as follows:

-  **Your domain name and associated SSL certificates**: We need the URL mainly to have an associated SSL certificate. We need the certificates to ensure that communications between your containers are encrypted (we pass traffic between your containers over https - for which we need the certs). Note that we will need an unique SSL certificate per domain that your app will be delivered on. So if you have two applications, you can either
 - Deploy each of them to their own domain (`app01.example.com` and `app02.example.com`) and provide the corresponding individual certificates for each domain or
 - Deploy each of them to their own domain (`app01.example.com` and `app02.example.com`) and provide a "splat" certificate (for `*.example.com`) in which case you can deploy any number apps and not have to buy additional certificates.

This is described in more detail in the following section on [domain names and certs](./domain_names.html)

-  **Public SSH Key**: You’ll need to create a public/private key pair to deploy code to the Catalyze PaaS. This keypair is used for the strong cryptography and that uniquely identifies you as a developer when pushing code changes. Remember that you need to provide the SSH key for each user that you intend to authorize to deploy code to the platform. Futher details on this is provided in the subsequent section on [SSH keys](./ssh_keys.html)

- **Environment variables**: Or "config vars" in [Heroku lingo](https://devcenter.heroku.com/articles/config-vars). Each app is likely to have to different variables and configurations such as S3 keys, environment names (dev, production etc.). These are specified (not in the code itself) outside as variables that can be set. More details are provided in the following section on [environment variables](./environment_variables.html)

