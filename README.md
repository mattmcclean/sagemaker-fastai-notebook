# SageMaker fast.ai notebook
Example project showing how to create a SageMaker notebook instance with the fast.ai library and course notebooks installed.

The notebook is designed to work with version 0.7 of the fast.ai library in order to run the fast.ai deep learning course v2 in early 2018 and also works with the latest version 1.0 of fast.ai with v3 of the fast.ai Deep Learning course generally available in 2019.

## Setup

Follow the instructions below to setup your IAM role and SageMaker Notebook Instance.

We will use [CloudFormation](https://aws.amazon.com/cloudformation/) to create our resources via a template file. To do this,

1. Click the **Launch Template** button below to open the AWS CloudFormation Web Console to create a new CloudFormation stack. Click through the options and select the SageMaker instance type. The **ml.t2.medium** option is part of the AWS Free Tier. See the SageMaker [pricing page](https://aws.amazon.com/sagemaker/pricing/) for more details.

The default instance type is **ml.p3.2xlarge** as this is required to train the fast.ai models quickly. Also you will need to select the version of the fast.ai library. Valid options are **0.7** and **1.0**. The default option is **0.7**. 

Region | Launch link
--- | ---
**eu-west-1** | [![CloudFormation](img/cfn-launch-stack.png)](https://eu-west-1.console.aws.amazon.com/cloudformation/home?region=eu-west-1#/stacks/create/review?filter=active&templateURL=https%3A%2F%2Fs3-eu-west-1.amazonaws.com%2Fmmcclean-public-files%2Fsagemaker-fastai-notebook%2Fcfn.yml&stackName=FastaiSageMakerNotebook)
**us-east-1** | [![CloudFormation](img/cfn-launch-stack.png)](https://us-east-1.console.aws.amazon.com/cloudformation/home?region=us-east-1#/stacks/create/review?filter=active&templateURL=https%3A%2F%2Fs3-eu-west-1.amazonaws.com%2Fmmcclean-public-files%2Fsagemaker-fastai-notebook%2Fcfn.yml&stackName=FastaiSageMakerNotebook)
**us-west-2** | [![CloudFormation](img/cfn-launch-stack.png)](https://us-west-2.console.aws.amazon.com/cloudformation/home?region=us-west-2#/stacks/create/review?filter=active&templateURL=https%3A%2F%2Fs3-eu-west-1.amazonaws.com%2Fmmcclean-public-files%2Fsagemaker-fastai-notebook%2Fcfn.yml&stackName=FastaiSageMakerNotebook)

Take note of the resources created including:
 - **IAM service role** allowing SageMaker access various AWS services
 - **SageMaker Notebook Instance** to run the fast.ai MOOC course notebooks.

![Screenshot](img/cfn-outputs.png)

2. Open the SageMaker Management console and select the SageMaker notebook instance named: **FastaiCourseNotebook** as per the screenshot below.
 
![Screenshot](img/sagemaker-nb.png)

3. Select the folder named **fastai-course-v2** or **fastai-course-v3** and open the notebooks to run through the course.

![Screenshot](img/jupyter-nb.png)