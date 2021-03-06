+++
title = "Concepts"
weight = 50
+++

{{% notice tip %}}
For a more detailed explanation on each of the below concepts, please checkout the documentation [CloudEndure Documentation]({{< ref "https://docs.cloudendure.com/" >}}).
{{% /notice %}}

#### Account

To start working with CloudEndure, you need to have an active CloudEndure Account and at least one License Package. An account can have multiple users managed by one Admin User.

#### Agent

The Agent is a software program that needs to be installed on the machines in the source location that needs to be replicated to the target location. In the lab, we will be seeing how to install Agent. 

#### License Package

Once you have a CloudEndure Account, you need to associate it with one or more License Packages. A License Package includes the licenses that are required for installing Agents on your Source machines. 

Licenses can be of type either of `Migration` or `Disaster Recovery`. Each License Package has a certain number of licenses. The number of licenses you need depends on the number of machines in the Source infrastructure that you want to use with. 

{{% notice tip %}}
You can use CloudEndure Migration to perform automated migration to AWS at no charge.
{{% /notice %}}



#### Project

A Project is the basic organizational unit for running a CloudEndure solution. Each Project applies one solution – either CloudEndure Migration or Disaster Recovery and has a specific Source infrastructure and a specific Target infrastructure. Each Project has its own Installation Token. This Installation Token is used to install Agents on the Source machines of the Project. Thus, the monitoring and managing of the Source machines is done at the Project level.

{{% notice info %}}
You cannot have CloudEndure Migration and Disaster Recovery projects under the same account.
 {{% /notice %}}

#### Recovery Point Objectives (RPO)

RPO is the last recoverable point in a solution. The greater the RTO, the more chance of data loss. RPO is measured based on the latest point in time in which block data was written to the source server volume(s) and successfully copied to the the customer’s target AWS account.

The CloudEndure Disaster Recovery agent continuously monitors the blocks written to the source server volume(s), and immediately attempts to copy the blocks across the network and into the replication Staging Area located in the customer’s target AWS account. This continuous replication approach enables sub-second RPO as long as the written data can be immediately copied across the network and into the replication Staging Area volumes.

#### Recovery Time Objective (RTO)

RTO is the time it takes the solution to recover from a source failure and boot the OS. RTO is measured from the recovery job start time until the recovered target server is booted and has network access on AWS.

When launching a recovery job, the CloudEndure Disaster Recovery orchestration process creates cloned volumes by using the replicated volumes in the replication Staging Area. During this process, CloudEndure Disaster Recovery also initiates a process that creates AWS-compatible volumes, which are attached to EC2 instances that can boot natively on AWS. Typically RTO of about 5-20 minutes depending on different environment factors such as OS Type, OS Configuration, Target Instance Performance and Target Volume Performance. Note: Pending OS updates can increase the RTO due to Windows automatically wanting to install those updates

#### Failover

Failover refers to the process of cutting over workloads to the target infrastructure during a test or disaster.

#### Failback

Once you have recovered your primary site after a disaster and resolved any issues associated, you can transfer business operations back to the source Infrastructure. The actual steps for failback depend on the source infrastructure. In case your source environment is AWS or VMWare, the steps are fully orchestrated. If your source infrastructure is physical or other public cloud providers, a Failback client will be necessary.