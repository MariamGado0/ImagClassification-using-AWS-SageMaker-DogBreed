# Image Classification using AWS SageMaker

Use AWS Sagemaker to train a pretrained model that can perform image classification by using the Sagemaker profiling, debugger, hyperparameter tuning and other good ML engineering practices. This can be done on either the provided dog breed classication data set or one of your choice.

## Project Set Up and Installation
Enter AWS through the gateway in the course and open SageMaker Studio. 
Download the starter files.
Download/Make the dataset available. 

## Dataset
The provided dataset is the dogbreed classification dataset which can be found in the classroom.
The project is designed to be dataset independent so if there is a dataset that is more interesting or relevant to your work, you are welcome to use it to complete the project.

### Access
Upload the data to an S3 bucket through the AWS Gateway so that SageMaker has access to the data. 

## Hyperparameter Tuning
ResNet50 Model:
* This project uses the ResNet-18 pre-trained model.
* The ResNet-50 is a convolutional neural network that is 18 layers deep. This pre-trained version of the network is trained on more than a million images from the ImageNet database The pretrained network can classify images into 1000 object categories, such as keyboard, mouse, pencil, and many animals.
* The dataset that we are going to use are an Image dataset which consist of images of dogs. 
* The dataset is divided into three parts training and validation and testing.

For hyperparameters, I tuned the two following ones :
 - Learning rate :
    -> default is 0.001 and the chosen range is =```[0.0001, 0.1]```
    ->  learning rate is a ContinuousParameter.
 - epochs: 
    -> defaut is 1e-08 and the chosen range is= ```[1e-9, 1e-8]```
    -> the epochs is a IntegerParameter
 - Weight decay:
    -> default is 0.01 and the chosen range is = ```[1e-3, 1e-1]```
 - Batch size :
    -> The chosen range is = ```[ 64, 128]```
    -> batch-size is a CategoricalParameter



**Best Training Jobs Hyperparameters after Tuning:**
![Best training job hyperparameters](image)


**Optimizer: [Adam]**
- Adam is a popular algorithm in the field of deep learning because it achieves good    results fast.
- learning_rate for Adam optimizer is a continuous parameter whose values are between ```[0.001, 0.01]```
- Adam is a popular algorithm in the field of deep learning because it achieves good results fast.
- Computationally efficient.
- Little memory requirements.
- Also Well suited for problems that are large in terms of data and/or parameters.

**Completed Training Jobs**


**Logs Metrics During the Training Process**


## Debugging and Profiling
- Debugging and Profiling was done with the help of the sagemaker.debugger module.
- Amazon SageMaker Debugger provides full visibility into training jobs of state-of-the-art machine learning models. 
- This SageMaker Debugger module provides high-level methods to set up Debugger configurations to monitor, profile, and debug your training job. 
- Configure the Debugger-specific parameters when constructing a SageMaker estimator to gain visibility and insights into your training job.



