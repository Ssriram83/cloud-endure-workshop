+++
title = "What We'll Build"
weight = 1
+++

### Architecture Overview

The architecture for this lab exercise is shown in the following diagram.
In this lab, we will learn how to set up and test Disaster Recovery for a sample 2-tier web application.
The Source Infrastructure will be setup in `us-east-1` AWS region by using cloudformation template and the Target DR site will be in `eu-west-1` AWS region. 

![Architecture](/lab1/DR_Architecture_Cross_Region.png?classes=shadow,border)

### High Level Steps

![CloudEndure Workflow](/lab1/CloudEndure_Workflow.png?classes=shadow,border&width=35pc)

1. **Setup**:
    - Setup the simulated source Infrastructure by using **CloudFormation template**. 
    - Setup CloudEndure project with the IAM User and Replication Settings. 
    - **Install CloudEndure Agents** on the Source machine.
    - **Configure Blueprint** for your recovered servers.
    - Wait until all machines enter Continuous Data Protection and **Test Target Servers**.
2. Initiate Failover.
3. Perform a Failback. 