+++
title = "Failover"
weight = 4

+++

Once you have completed the replication of volumes (status next to machine name says **Continuous Data Replication**) and set up the blueprint as per our requirements, we are then able to perform a **Test/Failover**.

This is how the project looks when it is in **Continous Data Protection** mode. 
![CDP Status](/lab1/instances_cdp_status.PNG?classes=shadow,border)

Every time you start the **Test/Failover**, CloudEndure  deletes any previously created instances and creates a **new Target instance** that is up to date with the latest copy of the data from the Source Environment.

{{% notice note %}}
According to best practice, and in real life, you should perform a **Test**  prior regularly. This is to identify potential challenges with your Blueprint configuration or with replicated volume conversion and address them.
{{% /notice %}}

1. Confirm that the volumes are fully replicated
   
    Confirm that the instance is in a state of **Continuous Data Replication** under the **DATA REPLICATION PROGRESS** column.

    If it's still replicating, wait until it reaches the **Continuous Data Replication** state. While waiting you can review <a href="https://docs.cloudendure.com/" target="_blank">CloudEndure documentation</a>.

2. From the **Machines** list select the DBServer and the Webserver that you want to Cutover, click **LAUNCH 2 TARGET MACHINE** button in the top right corner of the screen, then **Recovery Mode** and **CONTINUE** in the confirmation popup.

    ![CE-Failover](/lab1/recovery_mode_launch.png?classes=shadow,border)


    In the next screen, choose Recovery Point. With CloudEndure you can perform Point-in-Time Recovery. The frequency and number of Recovery Points are exact - every 10 minutes in the last hour, every hour in the last day and every day in the last month (60 in total per disk).

    ![Recovery Point](/lab1/choose_recovery_point.png?classes=shadow,border&height=350px)

    CloudEndure will now perform a final sync/snapshot on the volumes and begin the process of building new servers in the target infrastructure, all while maintaining data consistency. See the **Job Progress** screen for details.



    ![CE-job-progress](/lab1/job_progress.PNG?classes=shadow,border)

    Monitor the **Job Progress** log until you see **Finished starting converters** message (it should take 3-5 minutes). In the meantime you can review <a href="https://docs.cloudendure.com/#Configuring_and_Running_Disaster_Recovery/Performing_a_Disaster_Recovery_Failover/Performing_a_Disaster_Recovery_Failover.htm#Performing_a_Disaster_Recovery_Failover_and_Failback%3FTocPath%3DNavigation%7CConfiguring%2520and%2520Running%2520Disaster%2520Recovery%7CPerforming%2520a%2520Disaster%2520Recovery%2520Failover%2520and%2520Failback%7C_____0" target="_blank">CloudEndure Documentation  on the Failover process</a>.

    {{% notice tip %}}
If you don't see your job in the **Job Progress** window, refresh the browser (F5) and make sure to scroll to the top of the drop-down list of CloudEndure jobs.
{{% /notice %}}

1. Review resources created by CloudEndure in your AWS account
   
    Switch back to the **AWS Console** and navigate to your target AWS region if needed (eu-west-1/Ireland).
   
    You will see two additional instances managed by CloudEndure:
    - **CloudEndure Machine Converter** - used for conversion of the source boot volume, making AWS-specific bootloader changes, injecting hypervisor drivers and installing cloud tools. It's running for couple of minutes per each Test or cutover.
    - **CloudEndure Replication Server** - used to receive encrypted data from agents installed in the source environment. It's running when the replication of data is taking place.

    Both types of instances are fully managed by CloudEndure and are NOT accessible by users.

    As soon as the failover is finished, you will see 2 new EC2 instance on the list - this is your target Webserver and DB Servers created by CloudEndure. Make a note of its public and private IPs, as you will need them in the next step.
    ![Launched Instances](/lab1/launched_instances.png?classes=shadow,border)

    5. Select the webserver and copy its public DNS/IP and paste it in browser. It shall show the PHP landing page.

    ![Test PHP WebServer](/lab1/test_dr_site.png?classes=shadow,border&height=350px)

    This will confirm that, our test of the DR site is successful. Congratulations! You have set up your DR environment to AWS using CloudEndure.

    {{% notice tip %}}
If you want to know more about those servers, their purpose and network requirements see <a href="https://docs.cloudendure.com/#Preparing_Your_Environments/Network_Requirements/Network_Requirements.htm" target="_blank">CloudEndure Documentation</a>.
{{% /notice %}}
