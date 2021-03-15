+++
title = "Disaster Recovery Concepts"
weight = 1
+++

#### What is a Disaster?
Any event that prevents a workload or systems from fulfilling its business objectives in its primary deployed location is considered a disaster. These are the three main categories of disaster:

- Natural disasters, such as earthquakes or floods
- Technical failures, such as power failure or network connectivity
- Human actions, such as inadvertent misconfiguration or unauthorized/outside party access or modification

#### Disaster Recovery Options

Disaster recovery strategies can be broadly categorized into four approaches, ranging from the low cost and low complexity of making backups to more complex strategies using multiple active Regions.

![DR Options](https://docs.aws.amazon.com/whitepapers/latest/disaster-recovery-workloads-on-aws/images/disaster-recovery-strategies.png?classes=shadow,border)

CloudEndure Disaster Recovery uses the Pilot Light strategy, maintaining a copy of data and switched-off resources in an Amazon Virtual Private Cloud (Amazon VPC) used as a staging area. When a failover event is triggered, the staged resources are used to automatically create a full-capacity deployment in the target Amazon VPC used as the recovery location. Accordingly, CloudEndure’s Disaster Recovery solution
provides the resilience of a warm standby solution at the low cost of a cold standby solution. 

#### RPO & RTO

![RPO and RTO](https://docs.aws.amazon.com/whitepapers/latest/disaster-recovery-workloads-on-aws/images/recovery-objectives.png?classes=shadow,border)

#### Recovery Point Objectives (RPO)

RPO is the last recoverable point in a solution. The greater the RTO, the more chance of data loss. RPO is measured based on the latest point in time in which block data was written to the source server volume(s) and successfully copied to the the customer’s target AWS account.

The CloudEndure Disaster Recovery agent continuously monitors the blocks written to the source server volume(s), and immediately attempts to copy the blocks across the network and into the replication Staging Area located in the customer’s target AWS account. This continuous replication approach enables sub-second RPO as long as the written data can be immediately copied across the network and into the replication Staging Area volumes.

#### Recovery Time Objective (RTO)

RTO is the time it takes the solution to recover from a source failure and boot the OS. RTO is measured from the recovery job start time until the recovered target server is booted and has network access on AWS.

When launching a recovery job, the CloudEndure Disaster Recovery orchestration process creates cloned volumes by using the replicated volumes in the replication Staging Area. During this process, CloudEndure Disaster Recovery also initiates a process that creates AWS-compatible volumes, which are attached to EC2 instances that can boot natively on AWS. 
Typically, RTO is about 5-20 minutes depending on different environment factors such as OS Type, OS Configuration, Target Instance Performance and Target Volume Performance. Also, for Windows Operating System, pending OS updates can increase the RTO as Windows would want to automatically install those updates. 

#### Failover

Failover refers to the process of cutting over workloads to the target infrastructure during a test or disaster.

#### Failback

Once you have recovered your primary site after a disaster and resolved any issues associated, you can transfer business operations back to the source Infrastructure. The actual steps for failback depend on the source infrastructure. In case your source environment is AWS or VMWare, the steps are fully orchestrated. If your source infrastructure is physical or other public cloud providers, a Failback client would be necessary.