+++
title = "Preparing the Environment"
weight = 1
+++

### Preparing the Simulated Source Environment

To create the source infrastructure, go to AWS CloudFormation console AWS Console in `us-east-1` region Click on **Create Stack**, under **Choose a template** select Specify an **Amazon S3 template URL** and copy-paste below link and click **Next**.

`https://marketplace-sa-resources.s3.amazonaws.com/ctlabs/migration/LAMP2TierApp.yml`

Provide a Stack name as **source-simulated**

Enter the following Parameters to create the stack :

![CloudFormation Parameters](/lab1/source-simulated-app.png?classes=shadow,border)

- **MyClientIP**: Add your IP or CIDR to allow access via http (port 80) to the web application.
- Click **Next** → **Next** → **Create Stack**.
- It creates a VPC and deploys the 2-Tier LAMP stack(webserver & dbserver) and takes ~7 minutes to complete.

1. When stack **Status** will show **CREATE_COMPLETE**, please go to **Outputs** tab and copy the **DatabaseServer IP** and open the **WebsiteURL** in new browser tab.

2. It will open the Web app. Enter the DatabaseServer IP copied from last step in the text box and click on **Connect** button as shown below. The webserver shall connect to dbserver and show the connection message.

![Web Page](/lab1/DatabaseServerIP.png?classes=shadow,border)

*At this stage our source simulated environment is ready for the lab.

### Preparing your Target Environment

Navigate to to AWS CloudFormation console screen AWS Console in `eu-west-1` region. Click on **Create Stack**, under Choose a template select Specify an Amazon S3 template URL and copy-paste below link and click Next. 

`https://marketplace-sa-resources.s3.amazonaws.com/ctlabs/migration/MigrationTargetVPC.yml` 

Provide a Stack name as TargetVPC. Click Next, review the options you select and click Next again. Wait for the Stack Status to become CREATE_COMPLETE.
