+++
title = "Prepare Blueprint(s)"
weight = 3
+++

Blueprint includes parameters such as machine type (for example t3.medium), **subnet** where the machine should be running, **private IP** address and disk types.

To configure the Blueprint, go to the **Machines** tab and click on the name of the machine that you want to configure. Then navigate to the **BLUEPRINT** section.

### Server Blueprint

In the CloudEndure console, select Machines from the left sidebar. 1. Select the the server named webserver. This opens the details page to configure the machine blueprint with target instance options. 2. Fill the details as below * Machine Type: t3.small * Launch Type: On demand. * Subnet: Public Subnet 1…(TargetVPC). * Security Groups: TargetVPC-sgweb-xxx * Private IP address: Select create new. (It will choose new private IP from the target subnet selected) * Keep remaining options to Default except** Disks**: select SSD * Click SAVE BLUEPRINT


![Webserver-BluePrints](/lab1/webserver.png?classes=shadow,border)