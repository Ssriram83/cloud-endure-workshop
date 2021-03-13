+++
title = "CloudEndure Concepts"
weight = 2
+++

{{% notice tip %}}
For a more detailed explanation on each of the below concepts, please checkout the documentation [CloudEndure Documentation]({{< ref "https://docs.cloudendure.com/" >}}).
{{% /notice %}}

#### Account

To start working with CloudEndure, you need to have an active CloudEndure Account and at least one License Package. An account can have multiple users managed by one Admin User.

#### Agent

The Agent is a software program that needs to be installed on the machines in the source location that needs to be replicated to the target location. In the lab, we will be seeing how to install Agent. 

#### License Package

Once you have a CloudEndure Account, you need to associate it with one or more License Packages. A License Package includes the licenses that are required for installing Agents on your Source machines. 

Licenses can be of type either of `Migration` or `Disaster Recovery`. Each License Package has a certain number of licenses. The number of licenses you need depends on the number of machines in the Source infrastructure that you want to use with. 

{{% notice tip %}}
You can procure un-limited number of CloudEndure Migration Licenses free for 90 days.
{{% /notice %}}

#### Project

A Project is the basic organizational unit for running a CloudEndure solution. Each Project applies one solution – either CloudEndure Migration or Disaster Recovery and has a specific Source infrastructure and a specific Target infrastructure. Each Project has its own Installation Token. This Installation Token is used to install Agents on the Source machines of the Project. Thus, the monitoring and managing of the Source machines is done at the Project level.

{{% notice warning %}}
You cannot have CloudEndure Migration and Disaster Recovery projects under the same account.
 {{% /notice %}}