+++
title = "What We'll Build"
weight = 1
+++

### Architecture Overview

In this lab, we will learn how to set up and test Disaster Recovery for a sample 2-tier web application. 

![Architecture](/lab1/DR_Architecture_Cross_Region.png?classes=shadow,border)

#### High Level Steps

![CloudEndure Workflow](/lab1/CloudEndure_Workflow.png?classes=shadow,border&width=35pc)

1. **Setup**:
    - Prepare the environment by setting up the source infrastructure with sample 2-tier application by using **CloudFormation template**. 
    - Setup a **CloudEndure Disaster Recovery project**. 
    - **Install CloudEndure Agents** on the source machines.
    - **Configure Blueprint** for the servers in the target site.
2. Initiate a Test and an Actual Failover.
3. Perform a Failback.
4. Finally, we will be cleaning up all the resources that we created in this workshop.