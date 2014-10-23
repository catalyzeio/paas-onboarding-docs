# Domain Names & SSL Certificates

> I don't get what my signature is supposed to mean if we haven't had some kind of exchange.

> — Nana Visitor

###Overview

Because of the unique nature of SSL validation, provisioning SSL for your application is a multi-step process that involves several third-parties. You will need to:
- Purchase an SSL certificate from your SSL provider
- SSL endpoints are provisioned by default by Catalyze
- Upload the cert to Catalyze
- Update your DNS settings to reference the new SSL Endpoint URL

Additional details and steps are available  [here](https://devcenter.heroku.com/articles/ssl-endpoint). [This Stack Overflow answer](http://serverfault.com/questions/9708/what-is-a-pem-file-and-how-does-it-differ-from-other-openssl-generated-key-file) might also provide some additional context around some of the terms used in this section. 


A couple of points to pay attention to when you are purchasing the certs:
- While generating the CSR, the Common Name field must match the secure domain **exactly**. If you buy a certificate for `example.com`, it won't match or secure `www.example.com`. 
- So, if you want to deploy:
  - A single sub-domain such as `app01.example.com`, then buy a cert that matches that exactly
  - Multiple apps on different subdomains i.e. if you intend to deploy mutiple apps `app01.example.com` and `app02.example.com`, then buy the wildcard cert i.e. speify the URL during purchase as `*.example.com`

To deploy and secure your apps on Catalyze, we need the following pieces of information that need to be pasted into the appropriate areas in the dashboard screenshow shown below.

![Certs and domains](../pics/18.domains.certs.png)

- **URL / Domain name of the app**: As described above, you would use `app01.example.com` if you only intend to deploy the one app. If you intend to deploy several (dev, prod, qa etc.), you might choose to go with `*.example.com`

Quick note: please remember to click the blue (+) button to open the textbox to enter the information. Please also remember to click the blue (+) button *again* after entering the information. 

- **Corresponding SSL key**: Click on the blue (+) button in this box. This will open up a textbox. Paste the SSL key in here. And then click the blue (+) button again to close the box.
![Adding SSL key](../pics/20.add.ssl.key.png)

**SSL PEM**: You will also need the PEM for the Primary, Intermediate and RootCA authorities. Click on the blue **+** below each of them and paste the values in there. Details on how to go about generating and getting the PEMs are available [here](https://www.digicert.com/ssl-support/pem-ssl-creation.htm).Details and some explanation around what the PEM (also sometimes used interchangeably with .crt files) are also available [here](http://how2ssl.com/articles/working_with_pem_files/). Since various providers give this information to you differently. We'd recommend opening up the PEM file and copying and pasting the individual sections *including* the ``` ---- BEGIN ``` and ```END ----``` portions.

- **SSL Primary**: Click the blue (+) button and paste in the primary cert as shown below. Remember to include the ``` ---- BEGIN ``` and ```END ----``` portions. And remember to close it again after entering the info.
![Adding Primary Cert](../pics/21.add.primary.cert.png)
- **Intermediary**: This is optional and often depends on the certificate provider. We haven't provided you with a screenshot of this but if you have this information, please paste it in as well.
- **Rootca**: Again, click the blue (+), paste the cert including the ``` ---- BEGIN ``` and ```END ----``` portions. And remember to close it again after entering the info.
![Adding Root CA](../pics/22.add.root.ca.png)

After adding all these pieces of information, your screen should look something like this. Note that the Intermediary box has an *unlocked* icon on it as no information was entered there.
![Added all cert info](../pics/23.added.all.png)

After pasting the info above, click on the **Add Domain** button and you should see the domain you just added show up in the listing below as shown below.

![Certs and domains listing](../pics/24.domain.listing.png)

You're now ready to specify which users will have access to Catalyze to push code to the containers in your environment.

