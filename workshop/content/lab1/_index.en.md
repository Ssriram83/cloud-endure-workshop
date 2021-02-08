+++
title = "Lab1: Cross Region DR"
date = 2019-10-22T20:48:41+02:00
weight = 25
pre = "<b>- </b>"
+++

In this lab, we will be setting up a cross-region disaster recovery solution for a 2-tier LAMP Stack operation on AWS by using CloudEndure.

### Architecture Overview

The architecture for this lab exercise is shown in the following diagram.

![Architecture](/lab1/DR_Architecture.png?classes=shadow,border)

### High Level Steps

1. Set up Source Environment in AWS in us-east-1 region. To simulate a production workload, we will be creating a 2-tier LAMP stack (PHP Webserver, MySql Database) by using CloudFormation template. 
2. Set up network VPC required for Target DR site at eu-west-1(Ireland).
3. Configure CloudEndure Disaster Recovery Project to failover from us-east-1 to eu-west-1 region. 
