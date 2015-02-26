---
title: Define your environment
---

# Define your environment

> "So tell me what you want, what you really really want.."

> - The Spice Girls

The next step is defining what your environment needs to look like. This is where you specify the number and types of containers you need.

Let's take the case of a simple application which uses Ruby as the application (code) layer and Postgres as the database. As a quick side note, everything inside the Catalyze PaaS is called **"service"**.

Services can be of type:

- **code** (the programming language of your preference *viz: Ruby, Java, Python...*. This is the application container i.e. where the logic of your application resides)
- **database** (the database of your choice *viz: MongoDB, MySQL/Percona, and PostgreSQL*)
- **add-ons** (services that perform "ancillary" functions in your app *viz: memcache, redis or RabbitMQ*)

### Step 1: Define your code service

This is the application container i.e. where the logic of your application resides. A full listing of code services we support is available [here](//resources.catalyze.io/paas/getting-started/deploying-your-first-app/supported-languages-frameworks/). Please let us know from the links provided there if you'd like us to support additional ones. In the data entry fields provided, you would enter the following:

- **Name of your service**: (e.g. app01)
- **Service Type**: Since we want to build the application layer we'll select "Code" from the dropdown.
- ![Select Code Service](http://cdn2.dropmark.com/45280/5172f7da631a6d164be6f96ab9e92facd8849475/db_select-code.png)
- **Service Size**: Sizing essentially corresponds to the amount of RAM you wish to dedicate to this specific service. So, for example, if you know that your app has a pretty high volume of users, you would select 4GB or higher from the dropdown. Or you would select a smaller number if that was appropriate. Let's say we select 2GB in our example. Please ensure that your selections match your contract to minimize any confusion.
At the end of this set of selections, the screen would look something like this:
![Code Selections](http://cdn2.dropmark.com/45280/1dcc0fd76994a0844ee205cfd90d713f6c772d33/db_code-defined.png)
- **Add Service**: Click the Add Service button. You must click this to add it to the list. Once you do that, you will now see the service that you have just defined show up in the listing of services just above as shown below.
![Service Listing One](http://cdn2.dropmark.com/45280/091831e583b2ba067a507a425e4e4c552b6a43b8/db_added-services.png)

Note the **"High Availability"** and **"Code Scaling"** checkboxes to the right of your selections. Code Scaling essentially means that we will automatically create two identical containers of type code (based on your selections). So in the case of our example, if we'd selected the code option, the Catalyze PaaS would automatically provision two 2GB containers and wire them up to a Load Balancer. This would ensure that your app will be reliably utilized with a minimum of down-time (i.e. even if one container / app node fails for some reason, the Load Balancer would automatically remove that connection and route all traffic to the other node).

### Step 2: Define your database service
Similar to the above steps, you would now do the following to set up your database container:

- **Name of your service**: Since you are now defining a database service, you could potentially name it as `db01` or `my_awesome_db01`
- **Service Type**: Since this is a database service, you would pick "Database" from the Service Type dropdown
- **Service Image**: From this dropdown list, you would select the database that you would like to use. The listing shows the current set of databases we currently support. A full listing of databases we support is available [here](//resources.catalyze.io/paas/getting-started/deploying-your-first-app/supported-databases/). Please let us know from the links provided there if you'd like us to support additional ones. In the example we're working through, you would now select PostgreSQL from the dropdown listing.
- **Service Size**: Sizing essentially corresponds to the amount of RAM you wish to dedicate to this specific service. So, for example, if you know that your database has to support a pretty high volume of users, you would select 4GB or higher from the dropdown. Or you would select a smaller number if that was appropriate. Let's say we select 4GB in our example.
At the end of this set of selections, the screen would look something like this:
![Database selections](http://cdn2.dropmark.com/45280/68c21bf981908a32f868b54004919dc1f533a3b8/db_added-database.png)
- **Add Service**: click the Add Service button. You must click this to add it to the list. Once you do that, you will now see the service that you have just defined show up in the listing of services just above as shown below. You will now see two services being listed - the app01 service and the db01 service.
![Service Listing Two](http://cdn2.dropmark.com/45280/26cb47d493f4093fd168f8e8c0a2d4fe910621f5/db_datbase-in-table.png)

Note that the checkbox to the right now says "High Availability". This is a feature we're really proud of as we have configured PostgreSQL, MySQL / Percona and MongoDB in "HA" clusters with automatic replication. This specific feature will be expanded upon more in an upcoming publication.

###Step 3: Define your cache service (optional)

If your environment calls for a cache service like Memcached or Redis, then select as above. Making some basic selections, your screen will look something like this:

![Cache selection](http://cdn2.dropmark.com/45280/ce12d6967ffbba613dedf2f7f8cb8c54d0ee22b7/db_cache-selected.png)

Click on the Add Service button and you should see a listing of services as shown below. Note that HA is **NOT** available in cache selections in an automated fashion. Please drop us a note on the support channel and we'll be happy to discuss it more with you.

![Service Listing](http://cdn2.dropmark.com/45280/0c51d836f0da3c663020a543dad9afc52d5210f2/db_all-services.png)

After you're done defining your environment, click on "Continue to next step". This button will only be enabled if you've named your environment and have at least one code service enabled.

If you had selected HA in the code and database services, then your service listing would look something like this.

![Service Listing HA](http://cdn2.dropmark.com/45280/97b2dad30c3e9bc7f9f886c097899c4aada9bdf7/db_ha-services.png)
