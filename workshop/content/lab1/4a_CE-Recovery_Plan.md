+++
title = "(Optional) Recovery Plan"
weight = 5

+++

While dealing with a large number of machines you will find it easier to manage with the help of a recovery plan.
Recovery Plans let you pre-configure the order in which sets of machines are to be launched, and the launch wait times between these sets of machines. Recovery Plans can be initiated in Test Mode or Recovery Mode.

### Create a Recovery Plan
Create a Recovery Plan by navigating to **Recovery Plans** on the main left-hand navigation menu and then clicking on **NEW RECOVERY PLAN**.

![Recovery Plan](/lab1/recovery_plan_create.png?classes=shadow,border)

You will be redirected to the Recovery Plan creation view. Enter the name of your Recovery Plan as `LAMP Stack Recovery Plan`.

Recovery Plans are step-based. Each step is made up from a group of machines and wait times for machine launches. Click **ADD STEP** to add a step to your Recovery Plan.

In our infrastructure, since the webserver has a dependency with the DB server, it probably makes sense that step 1 is recovering DB server and Step 2 would be to recover Web Server. 

![Add Step](/lab1/add_step.PNG?classes=shadow,border)

Similarly add Web Server Step, but this time with a wait time of 120 seconds as I found that DB server takes about 2 minutes to get started. In an actual DR, you might want to adjust this step as per your experiental knowledge. 

This is how the **Recovery Plan** would look like

![Recovery Plan](/lab1/recovery_plan_created.png?classes=shadow,border)

Now that the recovery plan is created, you can choose whether you want to initiate the plan in **Test Mode** or **Recovery Mode**.

   {{% notice info %}}
Recovery Plans are not available while the Project is in Preparing for Failback mode.
{{% /notice %}}