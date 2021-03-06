---
title: Accessing your logging server
---

# Accessing your logging server

> "I don't even see the code anymore"

> — Cypher (Joe Pantoliano), The Matrix

Once you log into the dashboard, you can see the buttons for accessing your dedicated Logging containers next to your environment or from the Overview screen.

![Accessing Logging Environment](http://cdn2.dropmark.com/45280/a4d2194778ff67d0cd17d0a74e860bb371f2a525/db_logging-archive.png)

![Accessing Logging Environment](http://cdn2.dropmark.com/45280/20199e2b332fcf0bbe5132dcbe360261d0753e4f/db_logging-overview.png)

Click on the button (or link) and it will spawn a new window and you can view the logs from your application and environment there.

As soon as you login for the first time, you will see a screen which looks something like this:

![View Logging](/assets/img/pics/35.view.logging.png)

This is an extraordinarily powerful solution that we give to you and is worthwhile delving into a bit more detail.

###The Logging Stack

Under the covers, the dedicated logging server that you get is powered by the so-called ["ELK"](http://www.elasticsearch.org/) stack - [Elastic Search](http://www.elasticsearch.org/overview/elasticsearch/), [Logstash](http://www.elasticsearch.org/overview/logstash/) and [Kibana](http://www.elasticsearch.org/overview/kibana/).

This environment that we provision for you is dedicated to just you. Which means that you are free to set up customized dashboards, send specific logs to it, search and filter etc etc. It is worthwhile spending some time on these following links to get you started.

- [Overview of Kibana](http://www.elasticsearch.org/guide/en/kibana/current/index.html)
- [Understanding the query and filter syntax](http://www.elasticsearch.org/guide/en/kibana/current/working-with-queries-and-filters.html)
- [Creating / modifying dashboards](http://www.elasticsearch.org/guide/en/kibana/current/rows-and-panels.html)
- [Creating custom dashboards - Advanced](http://www.elasticsearch.org/guide/en/kibana/current/_dashboard_schema.html)
