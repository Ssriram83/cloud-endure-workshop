+++
title = "Failback"
weight = 5

+++
### CloudEndure Failback

Now the DR site is up. In an actual disaster situation, the primary site will be down and you will have to make network changes to divert traffic to the DR site. We discuss ways this can be automated in the lab [How to Automate your DR](/lab3/).


1. Click on the **PROJECT ACTIONS** menu and select **Prepare for Failback**
![Prepare for Failback](/lab1/prepare_for_failback.PNG?classes=shadow,border)

![Prepare for Failback](/lab1/prepare_for_failback_2.PNG?classes=shadow,border&width=20pc)

2. Once the action is performed the Project will display Preparing for failback to original Source next to the CloudEndure Disaster Recovery Project type.

3. The Machine Details View for the machines being failed back will also indicate that it's Waiting for boot from the Failback Client. The Machine Details View will show all of the steps that the Failback Client will undergo during the failback process. Use this view to monitor the progress of the failback and to troubleshoot any issues.
![Failback](/lab1/failback_machine_details.PNG?classes=shadow,border&width=20pc)

4. You will now need to launch new Target machines for your failed back machines. Check the box to the left of each machine name, click the **LAUNCH TARGET MACHINES** menu, and select **Recovery Mode**.

{{% notice info %}}
The source machines needs to be terminated or removed from the VPC, as the new servers will have the same information, and may cause collision if they are not removed. 
{{% /notice %}}


5. Once the Target machines have been launched, click the **PROJECT ACTIONS** menu and select **Return to Normal Operation** to reverse the direction of Data Replication back to its normal state (original Source to original Target.)

![Return to Normal](/lab1/return_to_normal.png?classes=shadow,border)

6. Once your machines enter Continuous Data Protection mode, the Failback process has been successfully completed.


{{% notice info %}}
After a successfull failover and a failback cycle, our machines will undergo the initiation sequence.
{{% /notice %}}

