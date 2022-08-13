# Overview

[![Python application test with Github Actions](https://github.com/alka077/Final_Project_CICD/actions/workflows/pythoapp.yml/badge.svg)](https://github.com/alka077/Final_Project_CICD/actions/workflows/pythoapp.yml)

This repositry demonstrate:

* Deploying the app in Azure CloudShell
* Deploying the app as a web server using Azure App Service.

Once anything has been changed (commits) in the github repositry, it will trigger an action for test automation (CI). A pipeline has been created using Azure DevOps tool, and also any changes will be tested in the pipeline and deployed to app service. All these steps are explianed well in the demo below.

# Project Plan

A link to a Trello board for the project https://trello.com/b/agz2gagW/udacity
A link to a spreadsheet that includes the original and final project plan project-management-template (1).xlsx


## Instructions
* Architectural Diagram
![github architecture](https://user-images.githubusercontent.com/106584802/184476688-0f61d6ba-8e32-4b4a-bf00-b25b3396d3f6.PNG)

![architecture](https://user-images.githubusercontent.com/106584802/184476699-5935657c-64ed-43e2-b123-9264a667ab61.PNG)


# Deploying the app in Azure CloudShell

* Azure Cloud Shell, clone the repo: git clone

![git clone cloud shell](https://user-images.githubusercontent.com/106584802/184476752-66b0eda1-b4f1-4a3b-a237-05c38122dacc.PNG)

* Create a virtual environment:

        python3 -m venv ~/.myrepo Activate the virtual environment:

        source ~/.myrepo/bin/activate Change into the new directory:

        cd udacity-azure-cicd 
* Install dependencies in the virtual environment and run tests:

![image](https://user-images.githubusercontent.com/106584802/184476793-38a75150-d7cf-4a09-99c0-7786ac029256.png)


* Enable github actions

![image](https://user-images.githubusercontent.com/106584802/184476816-a592d9b6-1cee-46b5-803b-ae920942c96d.png)


## Deploying the app as a web server using Azure App Service.

* Create an App Service in Azure. In this example the App Service is udacitywebapp and the resource group is Azuredevops, 

        az webapp up --resource-group Azuredevops --name udacitywebapp --loaction eastus --runtime "PYTHON:3.7"
    
    ![image](https://user-images.githubusercontent.com/106584802/184476879-8139bf8c-0662-47f5-8d7b-5f1a2aa216ea.png)

    ![image](https://user-images.githubusercontent.com/106584802/184476910-7d61b513-560f-48b5-a824-47660d0643d3.png)

* Make prediction using the below command:

                ./make_predict_azure_app.sh
                
     ![image](https://user-images.githubusercontent.com/106584802/184477175-a4ccefaf-077c-4254-89ae-62fe946b5836.png)


* Next, create the pipeline in Azure DevOps. More information on this process can be found here. The basic steps to set up the pipeline are:

* Go to https://dev.azure.com and sign in.

* Create a new public project. -Create a new service connection to Azure Resource Manager, select subscription and the app service.

* Create a new pipeline linked to your GitHub repo using GiThub YAML File.

![image](https://user-images.githubusercontent.com/106584802/184476987-18b64f14-4a1a-476e-af1a-831573d64f30.png)


* make Predict
    
    ![image](https://user-images.githubusercontent.com/106584802/184477006-997c75cd-df6b-49cf-9dfa-bdc6aca81c48.png)


* log Stream

    ![image](https://user-images.githubusercontent.com/106584802/184477013-089469b2-5072-40b6-bdb4-ca72ba5c2b27.png)

    ![image](https://user-images.githubusercontent.com/106584802/184477025-cec6cd1a-a402-43ec-b411-3a99a1f8fb0d.png)

* add the locustfile.py
* install locust using pip install locust
* run using locust -f locustfile.py  command
* open the httpe://localhost:8089 url in browser

    ![image](https://user-images.githubusercontent.com/106584802/184477092-d2e00e07-3bea-4824-b7aa-96b9c10b22e5.png)

    ![image](https://user-images.githubusercontent.com/106584802/184477109-04f76299-72d1-49e4-bef5-b0955f99cc5f.png)
    

Enhancements
to build an image of the app and push to an image registry(e.g acr) and then do a containerized deployment. The app could be deployed to a kubernetes cluster

Demo
https://youtu.be/bI2pAVOpCqw
