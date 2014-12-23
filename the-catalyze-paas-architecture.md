# The Catalyze PaaS Architecture

> Design is a funny word. Some people think design means how it looks. But of course, if you dig deeper, it's really how it works.

> — Steve Jobs


The Catalyze PaaS is comprised of:

* A dashboard
* Customer Pods
* Management Pods
* The Customer API and
* The Pod API

### The Dashboard
The dashboard is where you login and access your account, view the status of the environments and associated services that have been deployed and launch your dedicated logging and monitoring services and their associated UIs.

Details of the screens and activity to be performed within each is detailed under Section 3 - Deploying your first app.

### Customer Pods
A collection of hosts is called a Pod. We create collection of Pods which are meant to host our customer's applications, databases and other aspects of their environment. These Pods are IaaS-agnostic i.e. they can be deployed in AWS and/or Rackspace. More IaaS providers are in the works. The choice of IaaS providers is essentially dictated by customer demand and the willingness of the provider to sign a BAA. Customer Pods can be collections of bare metal hosts or VMs.

Customer Pods are where your applications and databases are deployed as Docker containers. A significant investment of time and effort has gone into securing and isolating the containers using AppArmor profiles (for example). Additional rules have been implemented such that containers enabling high availability (HA) scenarios are not deployed on the same host.

Connectivity between the various containers is SSL enabled and configured such that containers not belonging to you have no visibility to your containers (and vice versa). This is enabled by a proprietary mechanism which we intend to continually invest in and potentially open source soon.

Directions on what needs to happen is passed to the customer pods via the Pod API.

### Management Pods
A single Management Pod is deployed on each IaaS provider. In some cases, because of restrictions placed by the IaaS provider, more than one management pod could be deployed to manage multiple customer pods on the same IaaS provider. The management pod is responsible for deployment of the containers and passing the configurations to enable the customer specific containers to talk to each other securely.

Directions on what needs to happen is passed to the management pods via the Pod API as well.

### The Customer API
The Customer API's role is to translate the dashboard inputs into Pod API-speak. It additionally manages authentication and a few other tasks.

### The Pod API
The Pod API is the workhorse of the Catalyze PaaS. The core responsibilities of the Pod API is primarily to:
* receive inbound service configurations from the customer API
* transform them into dockerfiles and associated configurations
* pass the information to the internal "proxy" to wire up the containers with TLS enabled
* deploy containers across hosts based on various bidding rules - e.g. in an HA environment, do not deploy both postgres containers on the same host.

There are separate modules which handle specific capabilities such as orchestration, service registry, docker registry etc. We intend to detail a lot of this out in a series of blog posts.

