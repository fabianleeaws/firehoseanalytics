## Simulating Real-Time Data ingestion with Kinesis Data Generator (KDG)

For the sake of this lab, we will be using Amazon Kinesis Data Generator (KDG) to simulate a live stream of data. This a a tool open sourced by AWS available on: https://awslabs.github.io/amazon-kinesis-data-generator/web/help.html

### 1. Create a Cognito User

In order to use this tool, you'll need to create an Amazon Cognito user in your AWS account with permissions to send data to Kinesis. We provide a CloudFormation script to automate this for you.

CloudFormation templates allows you specify AWS resources with code, which the CloudFormation service can provision for you.

#### 1.1 Create Cognito User with CloudFormation

1.  Go to https://awslabs.github.io/amazon-kinesis-data-generator/web/help.html

2.  Select **Create a cognito User with CloudFormation**, which will launch it in a new browser tab

3.  Now complete the CloudFormation template to create the resources:

Ensure the region at the top right corner is **Oregon**:

![KDG Region](./imgs/02/02.png)

- Part 1: Select Template - Select **Next**
- Part 2: Specify Details - Enter **[iamuser-kinesis-generator]** as the stack name. Enter **[iamuser-kinesis-user]** as the username and choose a strong password. Select **Next**
- Part 3: Options - Leave the default settings and select **Next**
- Part 4: Review - Select the checkbox for **I acknowledge that AWS CloudFormation might create IAM resources**. Select **Create**

4.  To get the URL to access KDG, expands the Outputs dropdown:

![KDG URL](./imgs/02/03.png)

#### 1.2 Validate the newly created Cognito User

1.  Enter the **[iamuser-kinesis-generator]** and password you used earlier in the top right corner to login

### 2. Start Sending Data to Kinesis Firehose

We can now simulate a data stream with KDG

#### 2.1 Configure the Generator

Enter the following details:

1.  Region: **ap-southeast-1** (Singapore)
2.  Stream/Delivery stream: **[iamuser-firehose]**
3.  Records per second: 100

#### 2.2. Specify Data Model of records

1.

We're done! continue to [Lab 3 : Create & Deploy Your First Docker Image](./doc-module-03.md)
