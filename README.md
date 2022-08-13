# Overview

[![Python application test with Github Actions](https://github.com/alka077/Final_Project_CICD/actions/workflows/pythoapp.yml/badge.svg)](https://github.com/alka077/Final_Project_CICD/actions/workflows/pythoapp.yml)

This repositry demonstrate:

* Deploying the app in Azure CloudShell
* Deploying the app as a web server using Azure App Service.

Once anything has been changed (commits) in the github repositry, it will trigger an action for test automation (CI). A pipeline has been created using Azure DevOps tool, and also any changes will be tested in the pipeline and deployed to app service. All these steps are explianed well in the demo below.

## Architechture

# Project Plan

A link to a Trello board for the project https://trello.com/b/agz2gagW/udacity
A link to a spreadsheet that includes the original and final project plan project-management-template (1).xlsx


# Instructions
Architectural Diagram
![github architecture](https://user-images.githubusercontent.com/106584802/184476688-0f61d6ba-8e32-4b4a-bf00-b25b3396d3f6.PNG)

![architecture](https://user-images.githubusercontent.com/106584802/184476699-5935657c-64ed-43e2-b123-9264a667ab61.PNG)


# Deploying the app in Azure CloudShell

* Azure Cloud Shell, clone the repo: git clone
git clone cloud shell

* Create a virtual environment:

python3 -m venv ~/.myrepo Activate the virtual environment:

source ~/.myrepo/bin/activate Change into the new directory:

cd udacity-azure-cicd Install dependencies in the virtual environment and run tests:

make all

make all

github action build

Deploying the app as a web server using Azure App Service.
Create an App Service in Azure. In this example the App Service is cicd-nanodegree-haneen and the resource group is flask-app, you can either create it using Azure * * * cloudShell or the portal itself. In the Azure cloudShell type:

    az webapp up --resource-group Azuredevops --name udacitywebapp --loaction eastus

* Next, create the pipeline in Azure DevOps. More information on this process can be found here. The basic steps to set up the pipeline are:

* Go to https://dev.azure.com and sign in.

* Create a new public project. -Create a new service connection to Azure Resource Manager, select subscription and the app service.

* Create a new pipeline linked to your GitHub repo using GiThub YAML File.

*make_prediction

*udacityweapp net

* make_predict

* Running Azure App Service from Azure Pipelines automatic deployment

* Azure pipelines

* Output of streamed log files from deployed application

* log Stream

Enhancements
to build an image of the app and push to an image registry(e.g acr) and then do a containerized deployment. The app could be deployed to a kubernetes cluster

Demo
https://youtu.be/bI2pAVOpCqw
