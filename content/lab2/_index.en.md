+++
title = "Lab2: On-Premise Physical Data Center Disaster Recovery"
date = 2019-10-22T20:48:41+02:00
weight = 25
pre = "<b>- </b>"
+++


### Architecture Overview

This lab is very similar to Lab1 except for the failback step.  

The architecture for this lab exercise is shown in the following diagram.

![Architecture](/lab2/architecture_diagram.png?classes=shadow,border)

### High Level Steps

1. Set up a **Simulated Onpremise setup** in VirtualBox. 
2. Set up network VPC required for Target DR site at AWS cloud.
3. Configure CloudEndure Disaster Recovery Project to failover from on-premise to AWS DR Site and vice versa.
