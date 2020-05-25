# Deployment of a high-availability web app using Cloudformation

## Introduction

This CloudFormation templates deploy a high-availability web application.

The following diagram shows the infrastructure that is created in the process.

![Diagram](/images/diagram.png)

There are two templates and parameters files. One for the network infrastructure and the other for the servers infrastructure.

## How to run the templates using AWS CLI

First create the stack for the network infrastructure using the following command:

```
aws cloudformation create-stack --stack-name projectNetwork --template-body file://network.yml  --parameters file://network-param.json
```

Last create the final stack using the following command:

```
aws cloudformation create-stack --capabilities CAPABILITY_IAM CAPABILITY_NAMED_IAM --stack-name projectServers --template-body file://servers.yml  --parameters file://servers-param.json
```
