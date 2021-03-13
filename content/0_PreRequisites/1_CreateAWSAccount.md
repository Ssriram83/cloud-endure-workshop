+++
title = "Set up AWS Account"
weight = 1
+++
----------------

{{% notice warning %}}
Complete this section ONLY if you are running the workshop on your own. If you are at an AWS hosted event (such as re:Invent, GameDay, Workshop, or any other event hosted by an AWS employee) please proceed to the next step.
{{% /notice %}}


This lab assumes you have access to an **AWS Account** with <a href="https://docs.aws.amazon.com/IAM/latest/UserGuide/getting-started_create-admin-group.html" target="_blank">Administrator privileges</a>. To create a new AWS Account, please follow the <a href="https://aws.amazon.com/premiumsupport/knowledge-center/create-and-activate-aws-account/" target="_blank">How do I create and activate a new Amazon Web Services account?</a> article.

#### Creating a Policy for CloudEndure

This CloudEndure policy contains the necessary permissions for using AWS as your Target infrastructure.

##### To create an AWS policy for CloudEndure solution:

1. Sign in to [AWS Console](https://signin.aws.amazon.com/) with your AWS account.
   ![img](https://docs.cloudendure.com/Content/Resources/Images/Generating%20the%20Required%20AWS.png)

2. In the AWS Console, click on **Services** and then navigate to **Security, Identity & Compliance > IAM.**
   ![img](https://docs.cloudendure.com/Content/Resources/Images/Generating%20the%20Required%20AWS_1.png)

3. On the **Welcome to Identity and Access Management** page, select the **Policies** option from the left-hand navigational menu.
   ![C:\Users\Pavel-pc\Downloads\aws2.png](https://docs.cloudendure.com/Content/Resources/Images/CloudEndure%20-%20User%20Guide%20-Ch4%20Standalone%20-%20Draft1/Generating%20the%20Required%20AWS_2_553x284.png)

4. On the **Policies** page, click the **Create policy** button.
   ![C:\Users\Pavel-pc\Downloads\aws3.png](https://docs.cloudendure.com/Content/Resources/Images/CloudEndure%20-%20User%20Guide%20-Ch4%20Standalone%20-%20Draft1/Generating%20the%20Required%20AWS_3.png)

5. On the **Create Policy** page, click the **JSON** tab.
   ![C:\Users\Pavel-pc\Downloads\aws4.png](https://docs.cloudendure.com/Content/Resources/Images/CloudEndure%20-%20User%20Guide%20-Ch4%20Standalone%20-%20Draft1/Generating%20the%20Required%20AWS_4.png)

6. Navigate to the [CloudEndure](https://docs.cloudendure.com/Content/IAMPolicy.json). Copy the policy code. Paste the copied code into the JSON  field.

7. Click on **Review policy** at the bottom right of the page.
   ![img](https://docs.cloudendure.com/Content/Resources/Images/8.png)

8. On the **Review policy** page, enter a name for the new AWS-CloudEndure policy in the **Name** field. Enter an optional description in the **Description** field.
   ![img](https://docs.cloudendure.com/Content/Resources/Images/Generating%20the%20Required%20AWS_8.png)

9. Click the **Create policy** button at the bottom right of the page.
    ![img](https://docs.cloudendure.com/Content/Resources/Images/10.png)

10. You will be redirected back to the main **Policies** page and a confirmation stating that your new policy has been created will appear at the top of the page.
    ![C:\Users\Pavel-pc\Downloads\aws10.png](https://docs.cloudendure.com/Content/Resources/Images/CloudEndure%20-%20User%20Guide%20-Ch4%20Standalone%20-%20Draft1/Generating%20the%20Required%20AWS_10.png)

The next step is to create a new user, and then attach the policy you created to this user. During this procedure, you will be provided with an **Access key ID** and a **Secret access key,** which are the credentials you will need to enter into CloudEndure User Console.

#### Creating a New IAM User and Generating AWS Credentials

After creating an AWS policy which is based on CloudEndure's pre-defined policy, you will need to create a new IAM user and to attach the new policy to this user. You also need to provide this user with a **Programmatic** access type to enable the use of the new policy. At the end of this procedure, you will be provided with an **Access key ID** and **Secret access key**. It is important to save these values in an accessible and secured location, since they are required for running your CloudEndure solution.

##### Creating a new IAM User and generating AWS credentials

1. Navigate to **Users** on the left-hand navigational menu within **IAM**.
   ![C:\Users\Pavel-pc\Downloads\aws11.png](https://docs.cloudendure.com/Content/Resources/Images/CloudEndure%20-%20User%20Guide%20-Ch4%20Standalone%20-%20Draft1/Generating%20the%20Required%20AWS_11.png)

2. Click on **Add user**.
   ![C:\Users\Pavel-pc\Downloads\aws12.png](https://docs.cloudendure.com/Content/Resources/Images/CloudEndure%20-%20User%20Guide%20-Ch4%20Standalone%20-%20Draft1/Generating%20the%20Required%20AWS_12.png)

3. On the **Add user** page, set the following:

4. - **User name** - add a username for the new user.
   - **Access type** - check the **Programmatic** access option.
     ![C:\Users\Pavel-pc\Downloads\aws13.png](https://docs.cloudendure.com/Content/Resources/Images/CloudEndure%20-%20User%20Guide%20-Ch4%20Standalone%20-%20Draft1/Generating%20the%20Required%20AWS_13_132x47.png)

5. Click **Next: Permissions** at the bottom right of the page.
   ![img](https://docs.cloudendure.com/Content/Resources/Images/15.png)

6. On the **Set permissions** page, select the **Attach existing policies directly** option.
   ![img](https://docs.cloudendure.com/Content/Resources/Images/a2.png)

7. Locate the policy you created in the previous **Create a Policy for CloudEndure** section. You can either search for the policy in the **Search** box or locate it manually by scrolling through the policy list.
   ![img](https://docs.cloudendure.com/Content/Resources/Images/a3.png)

8. Once you have located the policy, check the box next to it.
   ![img](https://docs.cloudendure.com/Content/Resources/Images/Generating%20the%20Required%20AWS_17%20(1).png)

9. Click the **Next: Tags** button at the bottom right of the page.
   ![img](https://docs.cloudendure.com/Content/Resources/Images/a4.png)

10. You do not need to add any tags. Click the **Next: Review** button at the bottom right of the page
    ![img](https://docs.cloudendure.com/Content/Resources/Images/19.png)

11. On the **Review** page, verify that the correct **User name, AWS access type** (Programmatic access), and **Managed policy** are selected.
    ![img](https://docs.cloudendure.com/Content/Resources/Images/a5.png)

12. Click the **Create User** button at the bottom right of the page.
    ![img](https://docs.cloudendure.com/Content/Resources/Images/21.png)

13. A confirmation page will appear. This page provides you with your **Access key ID** and **Secret access key** which you will need to enter into the CloudEndure User Console.

14. Save your **Access key ID** and **Secret access key**. Then, to finish the procedure, click the **Close** button at the bottom right of the page.
    ![img](https://docs.cloudendure.com/Content/Resources/Images/25.png)

15. You will be returned to the **Users** page, and the details of the new user you created will be shown.
    ![img](https://docs.cloudendure.com/Content/Resources/Images/Generating%20the%20Required%20AWS_25.png)

You have now completed the process of generating the required AWS credentials. We will be using these credentials in the later sections. 