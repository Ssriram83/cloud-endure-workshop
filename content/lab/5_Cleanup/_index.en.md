+++
title = "Cleanup"
weight = 6

+++
-----------


### Deleting AWS resources deployed in this lab
To remove all resources you added in this lab, follow these steps:

1. On CloudEndure user console, go to Project Actions in the upper right. Choose Delete Current Project, as shown in the following screenshot.
![Delete Project](/lab1/delete_current_project.png?classes=shadow,border&width=20pc)
2. Go to CloudFormation AWS Console in eu-west-1 region and **delete the TargetVPC** stack.
3. Go to CloudFormation AWS Console in us-east-1 region and **delete the source-simulated** stack.