+++
title = "CloudEndure Configuration"
weight = 2
+++


To begin, you will need to configure CloudEndure with **AWS credentials** to access your AWS account and **replication destination** location (subnet) within target AWS account for the CloudEndure Replication Server.

### Configure AWS Credentials.

1. Login to CloudEndure Console at [https://console.cloudendure.com](https://console.cloudendure.com/)

    ![CE-login](/ce/CE-login.png?classes=shadow,border&height=200px)

    For **self-paced lab** - use your existing CloudEndure Account [CloudEndure Migration Account](https://console.cloudendure.com/#/register/register) and a new <a href="https://docs.cloudendure.com/#Getting_Started_with_CloudEndure/Working_with_Projects/Working_with_Projects.htm#Creating_a_New_Project%3FTocPath%3DNavigation%7CGetting%2520Started%2520with%2520CloudEndure%7CWorking%2520with%2520Projects%7C_____2" target="_blank">CloudEndure Project</a>. For **AWS Events** - use **CloudEndure Username** and **Password** listed in the <A href="https://dashboard.eventengine.run/dashboard" target="_blank">Event Engine - Team Dashboard</a>. If they are not shown on the <A href="https://dashboard.eventengine.run/dashboard" target="_blank">Event Engine - Team Dashboard</a>, please contact the presenter to provide you with the credentials.

2. Project Setup:

- Project name – AWS_CROSS_REGION_DR_DEMO
- Project type – select either Disaster Recovery.
- Target cloud – CloudEndure exclusively utilizes the AWS cloud as a Target infrastructure.
- License - select a License Package to associate with your Project.
Your Create New Project dialog box should look similar to the following. Click CREATE PROJECT when you are ready to create the new Project.
![Project](/lab1/PROJECT_CONFIGURATION.png?classes=shadow,border&height=350px)

3. Once the project is created successfully, Navigate to **Setup & Info** > **AWS Credentials** tab and enter **AWS Access Key ID** and **AWS Secret Access Key**.
   
    ![CloudEndure IAM Access and Secret Access Key](/ce/ce-self-service-accesskeys.png?classes=shadow,border&height=100px)

    For **AWS Event** - copy this information from your <A href="https://dashboard.eventengine.run/dashboard" target="_blank">Event Engine - Team Dashboard</a> - **CloudEndure AWS Credentials** section, it will look like on the screenshot below.  

    ![CloudEndure IAM Access and Secret Access Key](/ce/CE-credentials.png)

    Overwrite any values that are already present in **AWS Access Key ID** and **AWS Secret Access Key** fields.

4. Once you entered the **AWS Access Key ID** and **AWS Secret Access Key**, click the **SAVE** button.

### Configure Replication Settings.

Once you save your **AWS Credentials**, you will be automatically redirected to the **Setup & Info** > **REPLICATION SETTINGS** tab, this is where you configure details of the **CloudEndure Replication Server**.

{{% notice note %}}
Before proceeding **refresh the browser** to retrieve the latest information from your AWS account (you can do this by pressing the **F5** button or manually refreshing your browser by clicking on the refresh button).
{{% /notice %}}

![CE-Replication-setting](/lab1/replication_settings.png?classes=shadow,border&height=350px)

1. Update the configuration of the **REPLICATION SETTINGS** screen to match the values below:

    | Parameter                                  | Value                                                        |
    | ------------------------------------------ | ------------------------------------------------------------ |
    | Disaster Recovery Source                           | AWS US East Infrastructure                                         |
    | Disaster Recovery Target                           | AWS EU (Ireland)                                         |
    | Replication Server instance type           | Default                                                      |
    | Converter instance type                    | m5.large                                                     |
    | Dedicated replication servers              | Unchecked                                                    |
    | Subnet for the replication servers         | TargetVPC-public-a |
    | Security Group for the replication servers | Default CloudEndure Security Group                                                     |
    | Use VPN or DirectConnect (using a private IP) | Unchecked                                                |
    | Enable volume encryption                   | Checked                                                     |    
    | Choose the Volume Encryption Key you wish to apply to the Replication Servers' volumes | Default volume encryption key  |
    

2. Scroll to the bottom of the screen and click **SAVE REPLICATION SETTINGS** button. The dialog box Project Setup complete will appear.

![Show my how](/lab1/showMeHow.png?classes=shadow,border&height=250px)

Select SHOW ME HOW in the lower right. This opens guidelines to install CloudEndure agent on your source instances. In this lab, we will be using linux machines and your instructions will look like this:

![Instructions](/lab1/instructions.png?classes=shadow,border&height=250px)

### Install CloudEndure Agents

Go to the AWS **Systems Manager** **Run Command** console. Select Run Command in the upper right to start the installation process. To install CloudEndure agent on the Linux instance, choose the **AWS-RunShellScript* Command document.

![Run Shell](/lab1/AWS-RunShellScript.png?classes=shadow,border&height=350px)

For command parameters, once you selected **AWS-RunShellScript** copy the commands from the CloudEndure console & paste and run it.

![AWS-RunShellScriptParams](/lab1/AWS-RunShellScriptParams.png?classes=shadow,border)

For Targets, select Choose instance manually. Then check the checkbox next to Database & Web server instances to select them, as shown in the following screenshot.

![AWS-RunShellScriptTargets](/lab1/AWS-RunShellScriptTargets.png?classes=shadow,border&height=350px)

From the Output options, uncheck the Enable writing to an S3 bucket box and click on Run button. Wait until the status changes to Success.

![AWS-RunShellScriptsSuccess](/lab1/AWS-RunShellScriptSuccess.png?classes=shadow,border&height=350px)

Then navigate back to the **CloudEndure User Console** Browser Dashboard. Your instance now appears as an object in the Initial Sync phase. Wait until all instances reach **Continuous Data Replication** in the Data Replication Progress column.

![CloudEndure Machine Status](/lab1/machine_status_cloudendure.PNG?classes=shadow,border&height=350px)

While the instances are being replicated, let's move on to configuring a CloudEndure Target Machine Blueprint, which is the specification of your Target machine (replicated instance) that will be launched in AWS.
