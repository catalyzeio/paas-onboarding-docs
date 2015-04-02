---
title: The Catalyze PaaS Architecture
---

# The Catalyze PaaS Architecture

> Design is a funny word. Some people think design means how it looks. But of course, if you dig deeper, it's really how it works.

> — Steve Jobs


The Catalyze PaaS is comprised of:

* A dashboard
* Customer Pods
* Management Pods
* The Customer API
* The Pod API

### The Dashboard
The dashboard is where you sign in and access your Catalyze account. Here you can check the status of your environments, view associated services that have been deployed with your environment and launch your dedicated logging and monitoring services with their associated UIs.

### Customer Pods
A collection of hosts is called a Pod. We create collections of Pods which are meant to host our customer's applications, databases and other aspects of their environment. These Pods are IaaS-agnostic i.e. they can be deployed on AWS and/or Rackspace. More IaaS providers are in the works. The choice of IaaS providers is essentially dictated by customer demand and the willingness of the provider to sign a BAA. Customer Pods can be collections of bare metal hosts or VMs.

Customer Pods are where your applications and databases are deployed as Docker containers. A significant investment of time and effort has gone into securing and isolating the containers using AppArmor profiles. Additional rules have been implemented such that containers enabling high availability (HA) scenarios are not deployed on the same host.

Connectivity between the various containers is SSL enabled. These containers are configured such that ones not belonging to you have no visibility to your containers (and vice versa). This is enabled by a proprietary mechanism which we intend to continually invest in and potentially open source soon.

Directions on what needs to happen is passed to the customer pods via the Pod API.

### Management Pods
A single Management Pod is deployed on each IaaS provider. In some cases, because of restrictions placed by the IaaS provider, more than one management pod could be deployed to manage multiple customer pods on the same IaaS provider. The management pod is responsible for deployment of the containers and passing the configurations to enable the customer specific containers to talk to each other securely.

Directions on what needs to happen is passed to the management pods via the Pod API as well.

### The Customer API
The Customer API's role is to translate the dashboard inputs into Pod API-speak. It additionally manages authentication as well as other tasks.

### The Pod API
The Pod API is the workhorse of the Catalyze PaaS. The core responsibilities of the Pod API is primarily to:

* receive inbound service configurations from the customer API
* transform them into Dockerfiles and associated configurations
* pass the information to the internal "proxy" to wire up the containers with TLS enabled
* deploy containers across hosts based on various bidding rules - e.g. in an HA environment, do not deploy both Postgres containers on the same host

There are separate modules which handle specific capabilities such as orchestration, service registry, Docker registry etc.
