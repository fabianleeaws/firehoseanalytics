## Running Batch Jobs with AWS Batch

AWS Batch is a set of batch management capabilities that enables developers, scientists, and engineers to easily and efficiently run hundreds of thousands of batch computing jobs on AWS. AWS Batch dynamically provisions the optimal quantity and type of compute resources (e.g., CPU or memory optimized instances) based on the volume and specific resource requirements of the batch jobs submitted. With AWS Batch, there is no need to install and manage batch computing software or server clusters, allowing you to instead focus on analyzing results and solving problems. AWS Batch plans, schedules, and executes your batch computing workloads using Amazon EC2 and Spot Instances.

### 1. Configure AWS Batch

There are a few components you'll need to get familiar with AWS Batch:

1.  **Compute Environment**: Compute resources used to run the actual jobs. Environments are flexible as you can set it up to only use a particular type of EC2 instance like m4.large & c5.large, or specify the minimum/desired/maximum vCPUs and let AWS Batch pick the optimal instances. Because batch jobs do not usually require persistent running EC2 servers, spot instances can also be leveraged to increase cost effectiveness, with savings of up to 90% when compared to on-demand EC2 instances.

2.  **Job Definitions**: A job definition specifies how jobs are to be run. Think of it as a blueprint for the batch job which defines the resources required to run, ranging from vCPU, RAM, storage to the IAM permissions required so it can access other AWS Services programmatically. Job definitions can also be overwritten when submitted programmatically.

3.  **Job Queues**: When you submit an AWS Batch job, you submit it to a particular job queue, where it resides until it is scheduled onto a compute environment.

**Reference**: https://docs.aws.amazon.com/batch/latest/userguide/what-is-batch.html

#### 1.1 Create Compute Environment

1.  In the AWS Console, search for **Batch** under AWS Services and select it.

2.  If you currently don't have any resource sconfigured in AWS Batch, you'll be greeted with the **Getting Started** page. Select **Get started**:

![Batch Get Started](./imgs/03/01.png)

3.  However, we will not be using the getting started Wizard, but create each Batch component individually (Compute Environment, Job Definition etc.) to get a deeper understanding in the dependencies. Select **Cancel** at the bottom right:

![Cancel Wizard](./imgs/03/02.png)

4.  Select **Job Definition** from the left menu

5.  Enter **[iamuser-job-def]** as the **Job definition name**

We're done! continue to [Lab 3 : Running Batch Jobs with AWS Batch](./doc-module-03.md)

```

```
