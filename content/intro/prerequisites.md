+++
title = "Prerequisites"
weight = 20
+++

{{% notice warning %}}
Complete this section ONLY if you are running the workshop on your own. If you are at an AWS hosted event (such as re:Invent, GameDay, Workshop, or any other event hosted by an AWS employee) proceed to the next step.
{{% /notice %}}


### Self-paced learning environment

This lab assumes you have access to an **AWS Account** with <a href="https://docs.aws.amazon.com/IAM/latest/UserGuide/getting-started_create-admin-group.html" target="_blank">Administrator privileges</a>. To create a new AWS Accounts please follow the <a href="https://aws.amazon.com/premiumsupport/knowledge-center/create-and-activate-aws-account/" target="_blank">How do I create and activate a new Amazon Web Services account?</a> article.

 Once you have an AWS Account, the first step to getting started with CloudEndure is registering for the DR Solution. You can register for this directly through [AWS Marketplace.](https://docs.cloudendure.com/Content/Getting_Started_with_CloudEndure/Registering_to_CloudEndure_DR/Registering_to_CloudEndure_DR.htm#Getting_Started_with_CloudEndure/Registering_to_CloudEndure_Solutions/Registering_to_CloudEndure_Solutions.htm#Disaster)


CloudEndure Disaster Recovery is billed hourly per source server registered, irrespective of provisioned storage capacity. In addition to the CloudEndure Disaster Recovery subscription fee, you pay for the low-cost staging resources that CloudEndure Disaster Recovery creates (e.g., EC2, EBS) during continuous replication. Payment for fully provisioned resources is only required during disaster recovery drills or recovery mode.

The lab itself is estimated to take 1-2 hours to complete and expecct to cost you 3-4$. Below are the main components of the costs.

|   Component       | Charges                   |
|----------|--------------------|
| CloudEndure License subscription hourly rate per source server | $0.028 per hour |
| EC2 Servers (t3.large) | $0.0832 per Hour |
| EBS Volume (30GiB) | $0.08 GB-Month|
| EBS Snapshot size of  | $0.05 GB-month |

With these pre-requisites out of the way, lets start off by learning the basic concepts.