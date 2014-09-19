# Define connections between your containers

> The quality of the connections is the key to quality per se.

> — Charles Eames

Now that you have defined the various services within your environment, the next step is to tell the Catalyze PaaS how you would like them to be wired up. We ask you to make these connections explicitly so that we do not make assumptions on your behalf.

The convention we follow is data centric i.e. the store or source of data (e.g. database) **provides** data to the **consumer** of data (e.g. the application). So in the example that we've been working through, the PostgreSQL service provides data to the Ruby service. So you would select **db01** from the Data Provider drop down and **App01** from the Data Consumer dropdown. 

![Consumer Provider connections 1](../pics/connections.1.png).


Click the Add Connection button and you will see the graphical view of the connection shown on the right and listed below as well.

![Consumer Provider connections 2](../pics/connections.2.png).

If you make a mistake, delete the connection by clicking the red X next to the connection listing.

This is a simple app hence there is only one connection. If you had additional apps and other services like memcache, you would configure additional connections between the App01 service and the memcache service. Memcache being the source of data would be the Data Provider and the App01 would be the Data Consumer.
