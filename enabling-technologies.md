# Enabling technologies


>   I don’t look at myself as a commodity, but I’m sure a lot of people have.

>   — Marilyn Monroe

As an obvious starting point, commoditization of software components used to build web applications has made it much easier to support arbitrary customer environments. Web frameworks such as [node.js][2] and [Ruby on Rails][3] along with storage technologies like [MySQL][4], [PostgreSQL][5], and [MongoDB][6] (among others) on top of Linux have become so common that adding support for these services enables support for a **wide** variety of user applications.

[2]: <http://nodejs.org>

[3]: <http://rubyonrails.org/>

[4]: <http://www.mysql.com>

[5]: <http://www.postgresql.org/>

[6]: <http://www.mongodb.com/>

In addition, virtualization technologies make it cost-effective to run customer applications and services on a relatively small amount of hardware. Virtual machines provide a nice way of segregating customer environments but tend to be a bit heavyweight with resource usage. Containers and jails provide a lighter-weight solution but can be tricky to manage at larger scales without comprising security guarantees. [Docker][8] is an interesting take on the container approach; on the outset it appears to not provide much advantage over [Linux Containers][9], until you take a look at the additional management utilities provided by it and the ecosystem surrounding it. As it turns out, Docker solves a lot of the operational issues you would have if you attempted to build a platform for managing deployments using containers. It’s a young project but has improved very quickly, particularly in the months before its initial stable 1.0 release.

[8]: <http://www.docker.com>

[9]: <https://linuxcontainers.org/>
