# Motivation

>   People often say that motivation doesn’t last. Well, neither does bathing - that’s why we recommend it daily.

>   — Zig Ziglar

HIPAA compliance is painful. It is a major effort for a lot of our customers. The Catalyze Backend-as-a-Service product (BaaS, or sometimes just “the API”) provides a nice, easy-to-use method for spinning up new applications, but what about customers that have already invested in an application which uses their own code and/or backend? We can’t very well expect customers to completely rewrite their applications.

For these customers, we offer a standardized platform on which to host applications.  The platform takes care of all the prerequisites for HIPAA compliance while adding useful features like dedicated logging and monitoring. This offering has generated a lot of interest, which is not surprising given the features offered in combination with our core competencies.

The first few customers that signed on to the PaaS platform were migrated, deployed, and managed completely manually. This is a good way to prove out the utility of the platform but is incredibly difficult to scale to more customers.  Rather than using a brute-force approach to growing the platform (adding hordes of staff), we started working on ways to automate deploying and managing customers’ applications. The end result draws heavy inspiration from [Heroku][1] with some unique twists to satisfy the additions needed for HIPAA compliance.

[1]: <http://www.heroku.com>
