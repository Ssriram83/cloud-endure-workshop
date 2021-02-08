+++
title = "(optional lab) Automated DR by using CloudEndure APIs"
date = 2019-10-22T20:48:41+02:00
weight = 65
pre = "<b>- </b>"
+++


Automating disaster recovery (DR) has always been challenging. This workshop shows how you can automate all the steps that you performed in the previous labs by using CloudEndure DR. 

### Architecture Overview

In the labs we have seen so far, if an infrastructure or application outage occurs, a failover to AWS is executed by manually starting the process from the CloudEndure Console. In this lab, we will see how this process can be automated. 

![Automated DR](https://d2908q01vomqb2.cloudfront.net/fc074d501302eb2b93e2554793fcaf50b3bf7291/2019/10/07/DR1.png?classes=shadow,border)

In the above example, a webserver and database server have the CloudEndure Agent installed, and the disk volumes on each server replicated to a staging environment in the customer’s AWS account. 

 But this process can be automated as follows:

- A configured Route 53 health check monitors the endpoint of a webserver. 
- If the health check fails over a specified period, an alarm is raised to execute an AWS Lambda function to start the CloudEndure failover process. 
- In addition to health checks, Route 53 DNS Failover allows the DNS record for the webserver to be automatically update based on a healthy endpoint. 
- Now the previously manual process of updating the DNS record to point to the restored web server is automated.