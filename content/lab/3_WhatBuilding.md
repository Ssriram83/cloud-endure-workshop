+++
title = "What We'll Build"
weight = 1
+++

### Architecture Overview

In this lab, we will learn how to set up and test Disaster Recovery for a sample 2-tier web application running in AWS cloud. However the concepts and the process learnt in this lab can be applied to other environments as well. 

The following diagram shows the high level architecture.

![Architecture](/lab1/DR_Architecture_Cross_Region.png?classes=shadow,border)

The lab itself is estimated to take 1-2 hours to complete and expecct to cost you less than 5$. Below are the main components of the costs.

|   Component       | 
|----------|
| CloudEndure License subscription (hourly rate per source server) | 
| EC2 Servers (t3.large) | 
| EBS SSD Disks |
| EBS Snapshot  |

Given below the high-level steps invloved:

1. **Setup**:
    - Prepare the environment by setting up the source infrastructure with sample 2-tier application by using **CloudFormation template**. 
    - Setup a **CloudEndure Disaster Recovery project**. 
    - **Install CloudEndure Agents** on the source machines.
    - **Configure Blueprint** for the servers in the target site.
2. Initiate a Test and an Actual Failover.
3. Perform a Failback.
4. Finally, we will be cleaning up all the resources that we created in this workshop.

The below diagram explains the high level steps involved in this lab. 

![CloudEndure Workflow](/lab1/CloudEndure_Workflow.png?classes=shadow,border&width=35pc)