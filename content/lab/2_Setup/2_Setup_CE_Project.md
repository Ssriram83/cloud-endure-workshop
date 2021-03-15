+++
title = "CloudEndure Configuration"
weight = 2
+++


To begin, you will need to the **AWS credentials** that we [previously created](/0_prerequisites/1_createawsaccount.html). 

#### Step 1 - Create CloudEndure Project

1. Login to CloudEndure Console at [https://console.cloudendure.com](https://console.cloudendure.com/)

    ![CE-login](/ce/CE-login.png?classes=shadow,border&height=200px)

2. Project Setup:

- Project name – AWS_CROSS_REGION_DR_DEMO
- Project type – select Disaster Recovery.
- Target cloud – CloudEndure exclusively utilizes the AWS cloud as a Target infrastructure.
- License - select a License Package to associate with your Project.
Your Create New Project dialog box should look similar to the following. Click CREATE PROJECT when you are ready to create the new Project.
![Project](/lab1/PROJECT_CONFIGURATION.png?classes=shadow,border&height=350px)

3. Once the project is created successfully, Navigate to **Setup & Info** > **AWS Credentials** tab and enter **AWS Access Key ID** and **AWS Secret Access Key** that we generated in the [**PreRequisites Section**](/0_prerequisites/1_createawsaccount.html).
   
4. Once you entered the **AWS Access Key ID** and **AWS Secret Access Key**, click the **SAVE** button.

#### Step 2 - Configure Replication Settings

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
    

2. Scroll to the bottom of the screen and click **SAVE REPLICATION SETTINGS** button. The dialog window  **Project Setup Complete!** will appear.

In this lab, we will be using linux machines and your instructions will look like this:

![Instructions](/lab1/instructions.png?classes=shadow,border&height=250px)


{{% notice tip %}}
Whenever you forget the instructions, Click on  **Machines > MACHINE ACTIONS > Add Machines**. This opens guidelines to install CloudEndure agent on your source instances.
{{% /notice %}}


 