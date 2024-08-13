##  Build a ML Workflow for Scones unlimited on Amazon SageMaker
**Description**: This project has been built as a part of Udacity's AWS ML Fundamentals Program.

**Objective**:
To build a scalable and safe image classification model for Scones Unlimited using Amazon SageMaker.

### Amazon Web Services used:
- *Amazon Sagemaker*: Cloud-based machine-learning platform that allows the creation, training, and deployment by developers of machine-learning models on the cloud.
- *Amazon Lambda*: Serverless compute service for running code without having to provision or manage servers.
- *Amazon Simple Storage Service (S3)*: Cloud object storage.
- *Amazon Step Functions*: Visual serverless orchestration service that helps to create and manage workflows.
- *AWS Identity and Access Management (IAM)*: Service to securely manage identities and access to AWS services and resources.


### Key files

1. `starter.ipynb` : A Jupyter notebook containing complete script. It showcases a machine learning working workflow for Image Classification. 

The following steps have been implemented in the Jupter notebook:
- Data Staging
- Data Preprocessing
- Data Loading into S3 bucket
- Model Training
- Model Deployment
- Testing and Evaluation
- Data Visualization

2. `lambda.py` : A Python script comprising of all the three lambda functions that were used for the implementation of the ML Workflow.

Lambda functions used:

- `serializeImages.py` - A lambda function that takes in an object input from the S3 bucket, base64 encodes the object data and returns the serialized data as 'Image data' to the step function.

- `classifyImages.py` - A lambda function that performs image classification. It takes in the output of serializeImages.py function as input and returns inferences to the step function.

- `filterInferences.py` - A lambda function that performs inference filtration. It takes in the output of classifyImages.py function as input and filters the inferences based on low-confidence score.

3. `stepfunction.json` : An exported JSON file that contains the state machine (step function). AWS uses The Amazon States Language which is a JSON-based, structured language used to define a state machine.

4. `stepfunctions_graph.png` and `Screenshot Step Function Execution.png` : Images that showcase succesfull implementation of the step function, thus the ML workflow.


### Screenshot

|Step Function execution          |
|:-------------------------------:|
![Step Function](https://github.com/AnushkaKalra/Build-a-ML-Workflow-For-Scones-Unlimited-On-Amazon-SageMaker/blob/main/Screenshot%20Step%20Function%20Execution.png)|
