+++
title = "Install CloudEndure Agents"
weight = 3
+++

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
