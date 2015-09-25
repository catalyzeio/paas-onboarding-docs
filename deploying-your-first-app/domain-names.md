---
title: Domain Names & SSL Certificates
---

# Domain Names & SSL Certificates

> I don't get what my signature is supposed to mean if we haven't had some kind of exchange.

> — Nana Visitor

### Overview

Because of the unique nature of SSL validation, provisioning SSL for your application is a multi-step process that involves several third-parties. You will need to:

- Purchase an SSL certificate from your SSL provider
- SSL endpoints are provisioned by default by Catalyze
- Upload the cert to Catalyze
- Update your DNS settings to reference the new SSL Endpoint URL

Additional details and steps are available  [here](https://devcenter.heroku.com/articles/ssl-endpoint). [This Stack Overflow answer](http://serverfault.com/questions/9708/what-is-a-pem-file-and-how-does-it-differ-from-other-openssl-generated-key-file) might also provide additional context around the terms used in this section.

A couple of points to pay attention to when you are purchasing the certs:

- While generating the CSR, the Common Name field must match the secure domain **exactly**. If you buy a certificate for `example.com`, it won't match or secure `www.example.com`.

### So, if you want to deploy:

- A single sub-domain such as `app01.example.com`, then buy a cert that matches that exactly
- Multiple apps on different subdomains i.e. if you intend to deploy multiple apps `app01.example.com` and `app02.example.com`, then buy the wildcard cert i.e. specify the URL during purchase as `*.example.com`

To deploy and secure your apps on Catalyze, we need the following pieces of information that need to be pasted into the appropriate areas in the dashboard screenshot shown below.

![Certs and domains](http://cdn2.dropmark.com/45280/53bdc9f6fb5fb1a9e441c3b8afcd8ae4a73a2ad6/db_domain-name.png)

- **URL / Domain name of the app**: As described above, you would use `app01.example.com` if you only intend to deploy the one app. If you intend to deploy several (dev, prod, qa etc.), you might choose to go with `*.example.com`

Quick note: please remember to click the blue (+) button to open the textbox to enter the information.

- **Corresponding SSL Private Key**: Click on the blue (+) button in the box (as shown in the image below). This will open up a textbox. Paste the SSL key in there. Your SSL Private Key should look similar to:

  ```
-----BEGIN RSA PRIVATE KEY-----
MIIEpgIBAAKCAQEA63JKaFHoxPhcUm6IbF89dK9L525lrXEuVcWFSdM0pfyFwm4f
7RDWnldoZYAvRrs3BSvZOk99sfctJfXqRQ1YxaghJjgSCA3zUWDOO1RfHXkCGm4h
                              ...
43MF+8shntiNJTPSXxfz0I17iGJKRIZS8EW/E0+xvG8rPDwAkxCox6Q4ppzQjK7D
9OISeD6x/sfiIt1yM+kKa0juvJoEqZYWk8WZe7foAL1znOMtVmrbvCrx
-----END RSA PRIVATE KEY-----
  ```

![Adding SSL Private Key](http://cdn2.dropmark.com/45280/9061ec1c6f7270453b083f6fd3c4cf9e1776ff2c/db_ssl-key.png)

### SSL Certificate Chain

You will also need the PEM for the Primary, Intermediate and RootCA authorities. Click on the blue **+** below each of them and paste the values in there. Details on how to go about generating and getting the PEMs are available [here](https://www.digicert.com/ssl-support/pem-ssl-creation.htm). Details and some explanation around what the PEM (also sometimes used interchangeably with .crt files) are also available [here](http://how2ssl.com/articles/working_with_pem_files/). Since various providers give this information to you differently, we'd recommend opening up the PEM file and copying and pasting the individual sections *including* the ``` ---- BEGIN ``` and ```END ----``` portions. Your full SSL Certificate Chain should look similar to

  ```
-----BEGIN CERTIFICATE-----
MIID8DCCAtigAwIBAgIJAKABWQWr+7nKMA0GCSqGSIb3DQEBBQUAMFgxCzAJBgNV
BAYTAlVTMRIwEAYDVQQIEwlXaXNjb25zaW4xEjAQBgNVBAcTCU1pbHdhdWtlZTEh
                              ...
2afy/aCjKSRof5jQijqlhRnnydXcZTg1xboXaZIYTeORVEDIGco8o1lX1TQtNcHB
uHd9WQ==
-----END CERTIFICATE-----
-----BEGIN CERTIFICATE-----
vT0NTxC0MIGJBgNVHSMEgYEwf4AUv4GBeXNS1hielRyTmvO9PQ1PELShXKRaMFgx
CzAJBgNVBAYTAlVTMRIwEAYDVQQIEwlXaXNjb25zaW4xEjAQBgNVBAcTCU1pbHdh
                              ...
LX3qHXiV/tlijIosyqPDhPGNcQLym66Jux0EjdHw6vFqfOyvpNDqC2+gPENZ9bC+
pdRELP==
-----END CERTIFICATE-----
-----BEGIN CERTIFICATE-----
bnNpbjESMBAGA1UEBxMJTWlsd2F1a2VlMSEwHwYDVQQKExhJbnRlcm5ldCBXaWRn
aXRzIFB0eSBMdGQwggEiMA0GCSqGSIb3DQEBAQUAA4IBDwAwggEKAoIBAQDrckpo
                              ...
UejE+FxSbohsXz10r0vnbmWtcS5VxYVJ0zSl/IXCbh/tENaeV2hlgC9GuzcFK9k6
T32x9y==
-----END CERTIFICATE-----
  ```

![Adding Certificate Chain](http://cdn2.dropmark.com/45280/93f68829333c8e8f64300d4717b7a778f8ff3311/db_ssl-pem.png)


After pasting the info above, click on the **Add Domain** button and you should see the domain you just added show up in the listing below as shown below.

![Certs and domains listing](http://cdn2.dropmark.com/45280/5964ee65cef0c25fc550b9a122c512775e5d8173/db_domain-added.png)

You're now ready to specify which users will have access to Catalyze to push code to the containers in your environment.
