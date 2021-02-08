+++
title = "Failback"
weight = 6

+++
### CloudEndure Failback

Now the DR site is up. In an actual disaster situation, the primary site will be down and you will have to make network changes to divert traffic to the DR site. We discuss ways this can be automated in the lab [How to Automate your DR](/lab3/).


1. Click on the **PROJECT ACTIONS** menu and select **Prepare for Failback**
   .![img](https://docs.cloudendure.com/Content/Resources/Images/ed74.png?classes=shadow,border)
   ![img](https://docs.cloudendure.com/Content/Resources/Images/prepfail2.png?classes=shadow,border)

2. Click **CONTINUE** on the **Prepare for Failback** prompt.
   ![img](https://docs.cloudendure.com/Content/Resources/Images/prepfail3.png?classes=shadow,border)

3. Once the action is performed the Project will display **Preparing for failback to original Source** next to the CloudEndure Disaster Recovery Project type.
   ![img](https://docs.cloudendure.com/Content/Resources/Images/failb13.png?classes=shadow,border)
   The machines in the Machine List View will display **Waiting for boot from Failback Client** under the **DATA REPLICATION PROGRESS** column.
   ![img](https://docs.cloudendure.com/Content/Resources/Images/newfail1.png?classes=shadow,border)
   The Machine Details View for the machines being failed back will also indicate that it's **Waiting for boot from the Failback Client.** The Machine Details View will show all of the steps that the Failback Client will undergo during the failback process. Use this view to monitor the progress of the failbackand to troubleshoot any issues.
   ![img](https://docs.cloudendure.com/Content/Resources/Images/newfail2.png?classes=shadow,border)

4. Download the Failback Client, using the link from the **Replication Settings** section in the CloudEndure User Console under **Setup & Info**. To initiate replication the VirtualBox machine needs to be booted using this failback_client.iso

5. The Failback Client interface will launch and connect to the DHCP client. Upon connection, you will be prompted for your CloudEndure Installation Token. Input your installation token into the Failback Client

   

   **Note**: You can locate your installation token by navigating to **Setup & Info > Other Settings > Installation Token** in the CloudEndure Console.![img](https://docs.cloudendure.com/Content/Resources/Images/failb15.png?classes=shadow,border)

6. The Failback Client will attempt to automatically map the volumes on your machine. If successful, then the Failback Client will indicate that the volumes were mapped successfully and show the exact volume mapping that will be used.
   ![img](https://docs.cloudendure.com/Content/Resources/Images/failb4.png?classes=shadow,border)

7. Once the volumes have been mapped, the **Complete Volume Mapping** step will be marked as complete in the Machine Details View.
   ![img](https://docs.cloudendure.com/Content/Resources/Images/newfail72.png?classes=shadow,border)

8. The Failback Client will attempt to download and configure the CloudEndure Replication Software.
   Failback Client will attempt to configure the CloudEndure Replication Software.
   ![img](https://docs.cloudendure.com/Content/Resources/Images/failb7.png?classes=shadow,border)

   Finally, the [Failback Client](javascript:void(0);) will attempt to establish a connection with the CloudEndure [Agent](javascript:void(0);) running on your EC2 instance over port 1500. Once connection is established, replication will begin immediately.
   ![img](https://docs.cloudendure.com/Content/Resources/Images/failb20.png?classes=shadow,border)

   When you see the cloudendure console, you can now see this image. 

   ![img](https://docs.cloudendure.com/Content/Resources/Images/newfail9.png?classes=shadow,border)
   ![img](https://docs.cloudendure.com/Content/Resources/Images/newfail10.png?classes=shadow,border)

   

9. When initial replication is completed, the User Console will indicate that replication is in **Continuous Data Protection** mode. You will now need to launch new Target machines for your failed back machines. Check the box to the left of each machine name, click the **LAUNCH TARGET MACHINES** menu, and select **Recovery Mode.**

   When the  Recovery is finished, the Failback Client will indicate that the failback has been finished and that the machine will be rebooted. The Target machine will eject the Failback Clientand reboot into the new operating system.
   ![img](https://docs.cloudendure.com/Content/Resources/Images/failb17.png?classes=shadow,border)
   Once all machines are recovered, select **Project Actions** and click **Return to Normal Operation**. At the end of the operation, the [Failback](javascript:void(0);) project is configured to replicate into the [Target](javascript:void(0);) infrastructure again. The machines will start replicating into the [Target](javascript:void(0);) infrastructure.
   ![img](https://docs.cloudendure.com/Content/Resources/Images/pre10%20(1)%20(1).png?classes=shadow,border)
   ![img](https://docs.cloudendure.com/Content/Resources/Images/rep7.png?classes=shadow,border)

10. Click **CONTINUE** on the **Return to Normal** dialog.
    ![img](https://docs.cloudendure.com/Content/Resources/Images/pre11.png?classes=shadow,border)

11. Your machines will yet again undergo the initiation sequence.
    ![img](https://docs.cloudendure.com/Content/Resources/Images/pre12.png?classes=shadow,border)

12. Once your machines enter **Continuous Data Protection** mode, the [Failback](javascript:void(0);) process has been successfully completed.
    ![img](https://docs.cloudendure.com/Content/Resources/Images/pre13.png?classes=shadow,border)

{{% notice info %}}
After a failover and a failback cycle, our machines will yet again undergo the initiation sequence.
{{% /notice %}}

