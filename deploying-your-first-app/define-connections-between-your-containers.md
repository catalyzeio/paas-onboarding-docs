---
title: Define connections between your containers
---

# Define connections between your containers

> The quality of the connections is the key to quality per se.

> - Charles Eames

Now that you have defined the various services within your environment, the next step is to tell the Catalyze PaaS how you would like them to be wired up. We ask you to make these connections explicitly. Only those connections will be set up and only those containers will be able to talk to each other. We do this to maximize security and isolation of your containers. 

The convention we follow is data centric i.e. the store or source of data (e.g. database) **provides** data to the **consumer** of data (e.g. the application). So in the example that we've been working through, the PostgreSQL service provides data to the Ruby service. So you would select **db01** from the Data Provider drop down and **App01** from the Data Consumer dropdown. (**Note:** The diagram on the right is fully interactive. To add a connection, simply drag and arrow from a data provider to a data consumer)

![Consumer Provider connections 1](http://cdn2.dropmark.com/45280/16a606818be74b31d8854a79e232f4927ef3dbe1/db_connection-dropdown.png)

Click the Add Connection button and you will see the graphical view of the connection shown on the right and listed below as well.

![Consumer Provider connections 1](http://cdn2.dropmark.com/45280/b74f08cecf384d7862ba60f5326d7a4fa5cfff65/db_first-connection.png)

If you make a mistake, delete the connection by clicking the red X next to the connection listing.

Similarly, you would configure additional connections between the app01 service and the memcache service. Memcache, being the source of data, would be the Data Provider, and App01 would be the Data Consumer. So at the end of this step, you would get a connection diagram and listing that looks like this.


![Consumer Provider connections 2](http://cdn2.dropmark.com/45280/0d03b4064d809cf32a9dd703c99e23eb12acba0c/db_second-connection.png)

If you had selected HA on the screens earlier, note that the HA "boxes" are represented as just *one* box. You **don't** have to explicitly define the connections between *all* the pairs.

![Connections HA](http://cdn2.dropmark.com/45280/b559ab282f8d84ddbd266010db041554652274a3/db_thrid-connection.png)

So, if we had a complicated architecture which included *all* of the above services and connections, perhaps your screen would look something like this.

![Complex connections](http://cdn2.dropmark.com/45280/4a728c2da96a9b58549fc573584aed123e6f2f6c/db_fourth-connection.png)

Once this has been done, you're ready to move on to defining environment specific variables, SSH keys and SSL certs.

