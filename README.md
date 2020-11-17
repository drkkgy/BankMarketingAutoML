*NOTE:* This file is a template that you can use to create the README for your project. The *TODO* comments below will highlight the information you should be sure to include.


# BankMarketingAutoML
## Table of Content
* [Overview](##overview)
* [Architectural Diagram](#architectural-diagram)
* [Key Steps](#key-steps)
* [Screen Recording](#screen-recording)
* [Future Improvements](#screen-recording)
* [Standout Suggestions](#standout-suggestions)

## Overview ##

This Projet involves analysing the Bank Marketing Dataset. Here we are trying to use this data to perform classification and predict whether a Term Deposit will be opened or not by the potential customer.
We are leveraging the Azure AutoML service to automatically generate the best fitting model for our application and deploying this model as an endpoint to perform prediction. We also create an Azure Pipline
for training this model as required to ensure its accuracy.
  
## Architectural Diagram

### Architectural Diagram
![Architectural Diagram](./Architecture_Diagram.PNG?raw=true "Architectural Diagram")

## Key Steps

### Step-1 Automated ML Experiment :-
We create a Data Set for the given BankMarketing dataset url. Then we feed this data into AutoML Service to automaticall fit and create a model capable of classifying and prediction whether a Term Deposit will be opened or not by the potential customer.

### Screenshots:- 
#### Registered Dataset:-
![Dataset](./Dataset.PNG?raw=true "Dataset")
#### Expereiment Completed:-
![Experiment_Completed](./Experiment_Complete.PNG?raw=true "Experiment_Completed")
#### Best Model:-
![Best_Model](./Best_Model.PNG?raw=true "Best_Model")

### Step-2 Deploy the Best Model:-
We deploy the best model identifed by autoML on an Azure Container Instacne (ACI) with Authentication option enabled

### Step-3 Enable Application Insights :-
We enable the application insights for our deployed model endpoint using Azure CLI 

### Screenshots:- 
#### App-Insight-Resource:-
![App-Insight-Resource](./App-Insight-Resource-cli.PNG?raw=true "App-Insight-Resource")
#### Application Insights Enabled:-
![App-Insights](./App-Insights.PNG?raw=true "App-Insights")
#### App Insight Logs:-
![Logs](./Logs.PNG?raw=true "Logs")

### Step-4 Swagger Documentation :-
Here we setup swagger and download Swager.json file and try to consume are model using Swagger API's

### Screenshots:- 
#### Swagger On Localhost:-
![Swagger-1](./Swagger-1.PNG?raw=true "Swagger-1")

![Swagger-2](./Swagger-2.PNG?raw=true "Swagger-2")

![Swagger-3](./Swagger-3.PNG?raw=true "Swagger-3")

![Swagger-4](./Swagger-4.PNG?raw=true "Swagger-4")

### Step-5 Consume Model Endpoint :-
We interact with the exposed endpoints for our model to perfrom prediciton on realtime data values sent in JSON format to receive a 
prediction response.

### Screenshots:- 
#### endpoint.py File result:-
![endpoint](./endpoint.PNG?raw=true "endpoint")
#### Benchmarking:-
![Benchmark](./Benchmark.PNG?raw=true "Benchmark")

### Step-6 Create Publish and Consume Pipeline :-
Here we finally deploy the azure pipeline to train the model and expose it to an endopoint

### Screenshots:- 
#### Swagger On Localhost:-
![Pipeline](./Pipeline.PNG?raw=true "Pipeline")

![Pipeline-endpoint](./Pipeline-endpoint.PNG?raw=true "Pipeline-endpoint")

![AutoML-BankmarketingDataset](./AutoML-BankmarketingDataset.PNG?raw=true "AutoML-BankmarketingDataset")

![Published-Pipeline](./Published-Pipeline.PNG?raw=true "Published-Pipeline")

![RunDetails](./RunDetails.PNG?raw=true "RunDetails")

![Running_Pipeline](./Running_Pipeline.PNG?raw=true "Running_Pipeline")

## Screen Recording ##

### Link to Screen Cast
[Click Here](https://youtu.be/ykBXimy5J2Y)

## Future Improvements 
  * We can increase the Exit Criterion from 1 hour to 3  hours(Default ) or even more to find 
  even more accurate models.
  * We can collect more data which can enable the model to be more accurate and current. 
  * We can also enable Data drift tracking to ensure accuracy of the model.

## Standout Suggestions
  * Implemented the Benchmarking Scripts to benchmark the endpoint
