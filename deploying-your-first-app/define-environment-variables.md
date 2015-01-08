---
title: Define environment variables
---

# Define environment variables

> To be is to be the value of a variable.

> — Willard Van Orman Quine

OK, we're almost there. The last thing remaining is defining the list of environment variables that you would like defined in your app. The general format that needs to be followed is:
```
VARIABLE_NAME=WHATEVER_the_VAlU3
```

Example of environment variables include:
- `ENVIRONMENT_NAME` e.g. `ENVIRONMENT_NAME`-`development`
- `S3_KEY` e.g. `S3_KEY`-`8N029N81`
- `S3_SECRET` e.g. `S3_SECRET`-`9s83109d3+583493190`
- `NODE_ENV` e.g. `NODE_ENV`-`development`
- `RAILS_ENV` e.g. `RAILS_ENV`-` production`
- `RACK_ENV` e.g. `RACK_ENV`-`production`

and so on. More details can be got from [here](https://devcenter.heroku.com/articles/config-vars).

**Note that these environment varibles are services specific**. So you will need to add variables specific to each app. In this example, we only have one app. If you have multiple apps, you will need to click on the individual app tabs and enter the variables there separately.

You will note that the **app01** service has be pre-selected so that all the variables that you enter first correspond to app01. Put the ```VARIABLE_NAME``` in one box and the value ```WHATEVER_the_AlU3``` in the corresponding box next to it. 

![Enter ENV Variables](/assets/img/pics/28.add.env.var.png)

Click the green **Add Variable** button each time. You will see a listing of the environment variables show up on each click above the text boxes.
![Listing of ENV Variables](/assets/img/pics/29.listing.of.env.vars.png)

To add variables for any additional apps that you might have, please click on the tab on the left with that name and enter the variables and values as described above.


That's it!
