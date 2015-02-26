---
title: Enabling technologies
---

# Enabling technologies

> I don't look at myself as a commodity, but I'm sure a lot of people have.

> - Marilyn Monroe

As an obvious starting point, the commoditization of software components used to build web applications has made it much easier to support arbitrary customer environments. Web frameworks such as [node.js](//nodejs.org) and [Ruby on Rails](//rubyonrails.org/) along with storage technologies like [MySQL](//www.mysql.com), [PostgreSQL](//www.postgresql.org/), and [MongoDB](//www.mongodb.com/) (among others) on top of Linux have become so common that adding support for these services enables support for a **wide** variety of user applications.

In addition, virtualization technologies make it cost-effective to run customer applications and services on a relatively small amount of hardware. Virtual machines provide a nice way of segregating customer environments but tend to be a bit heavyweight with resource usage. Containers and jails provide a lighter-weight solution but can be tricky to manage at larger scales without comprising security guarantees. [Docker](//www.docker.com) is an interesting take on the container approach; on the outset it appears to not provide much advantage over [Linux Containers](//linuxcontainers.org/), until you take a look at the additional management utilities provided by it and the ecosystem surrounding it. As it turns out, Docker solves a lot of the operational issues you would have if you attempted to build a platform for managing deployments using containers. It's a young project but has improved very quickly, particularly in the months before its initial stable 1.0 release.