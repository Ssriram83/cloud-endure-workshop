+++
title = "CloudEndure Blueprint"
weight = 4
+++


Blueprint includes parameters such as machine type (for example t3.medium), **subnet** where the machine should be running, **private IP** address and disk types.

To configure the Blueprint, go to the **Machines** tab and click on the name of the machine that you want to configure. Then navigate to the **BLUEPRINT** section.

### Webserver Blueprint

In the CloudEndure console, select Machines from the left sidebar. 
1. Select the the server named webserver. This opens the details page to configure the machine blueprint with target instance options. 
2. Fill the details as below

| Parameter                                  | Value                                                        |
    | ------------------------------------------ | ------------------------------------------------------------ |
    | Machine Type | t3.small|
    | Launch Type                          | On demand |
    | Subnet                          | Public Subnet 1 …(TargetVPC)|
    | Security Groups                          | TargetVPC-sgweb-xxx|
    | Private IP address                          | Select create new.(It will choose new private IP from the target subnet selected)|
    |Disks                        |  select SSD |

 ** Keep remaining options to Default except
  
  Click SAVE BLUEPRINT


![Webserver-BluePrints](/lab1/webserver.png?classes=shadow,border)

### DB Server Blueprint

In the CloudEndure console, select Machines from the left sidebar. 
1. Select the the server named dbserver. This opens the details page to configure the machine blueprint with target instance options. 
2. Fill the details as below 

| Parameter                                  | Value                                                        |
    | ------------------------------------------ | ------------------------------------------------------------ |
    | Machine Type | t3.small|
    | Launch Type                          | On demand |
    | Subnet                          | Private Subnet 1A.(TargetVPC)|
    | Security Groups                          |TargetVPC-sgdatabase-xxx|
    | Private IP address                          | Select create new.(It will choose new private IP from the target subnet selected)|
    |Disks                        |  select SSD |

 ** Keep remaining options to Default except
  
  Click SAVE BLUEPRINT

Now that we have set the blueprints, we are ready to do the Recovery Testing or the actual Recovery.