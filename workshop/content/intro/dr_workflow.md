+++
title = "Disaster Recovery Workflow"
weight = 50
+++

The general DR implementation process can be summarized as below:

1. Register for a CloudEndure account
2. Set up a project and define replication settings.
3. Install the CloudEndure Agent on the Source machine.
4. Configure the Target machine Blueprint for each machine.
5. Wait until all machines enter Continuous Data Protection.
6. Test the Failover by creating one or more Target machines.
7. Initiate a Failover.
8. To recover your data, initiate a Failback. This step terminates Data Replication.
9. Return to normal operations.

![Workflow](/intro/workflow.png?classes=shadow,border&height=250px)

The below video gives a quick demo of the above process flow.

{{< youtube i6F2eUXDuRM >}}
