# Accessing monitoring

> "It's alive. It's alive..."

> — Dr. Henry Frankenstein (Gene Wilder), Frankenstein (1931)

Once you log into the dashboard, you can see the buttons for accessing you dedicated Monitoring containers next to you environment or from the Overview screen.

![Accessing Monitoring Environment](../pics/35.accessing.monitoring.png)

Click on the button (or link) and it will spawn a new window and you can view the status from your application and environment there. The first time you login, the screen will look something like this.

![View monitoring](../pics/36.view.monitoring.png)

Any and all alerts will show up on this page. This screenshot currently has no alerts raised.

You can additionally click on the icons at the top right or the identical ones on the left nav to see the the clients (containers) being monitored and the checks that have been automatically put into place.

![View clients monitored](../pics/37.view.clients.sensu.png)


###The Monitoring solution
Just like the logging environment, the monitoring environment that has been provisioned is also dedicated just for you. Currently, you can view statuses of the containers and your overall environment. However, the solution is extremely powerful and configurable. We're working to allow you to add additional services to monitor (including processes within your application), set up notifications etc. programmatically via the code that you check in. 

The solution that we use is called [Sensu](http://sensuapp.org/#features).
