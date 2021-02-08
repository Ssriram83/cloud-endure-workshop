+++
title = "Preparing the Environment"
weight = 1
+++

### Preparing the Simulated Source Environment

To create the source infrastructure, 

1. Download and install [VirtualBox](https://www.virtualbox.org/wiki/Downloads). 
2. Download LAMP OVA file from [Bitnami](https://bitnami.com/stack/lamp/virtual-machine).
3. Import the OVA to your virtualbox by **Select File** and **Import Appliance** and selecting your OVA. Leave all the default settings as it is. If the import is successful, then you must see a screen as

![PHP Lamp Stack](/lab2/php_lamp.PNG?classes=shadow,border)

4. Next, prepare your AWS Target Environment. Navigate to to AWS CloudFormation console screen AWS Console in `eu-west-1` region. Click on **Create Stack**, under Choose a template select Specify an Amazon S3 template URL and copy-paste below link and click Next.

`https://marketplace-sa-resources.s3.amazonaws.com/ctlabs/migration/MigrationTargetVPC.yml` 

Provide a Stack name as TargetVPC. Click Next, review the options you select and click Next again. Wait for the Stack Status to become CREATE_COMPLETE.