## `IMPORTANT`
### This repository is **ARCHIVED** and replaced by https://github.com/aws-samples/aws-alien-attack

# AWS Alien Attack App

**DISCLAIMER:** AWS Alien Attack App, and all complementary resources are provided without any guarantees, and you're not recommended to use it for production-grade workloads. The intention is to provide content to build and learn.


## What is this?
This is a Alien Attack game with serverless back-end based on AWS.

Before running it, you need to deploy the back-end, which can be created by following the instructions at [Alien Attack Workshop](https://github.com/fabianmartins/alienattack.workshop).

After deploying the back-end, you need to update the file `./resources/js/aws-config` with the required data.

~~~
const DEBUG = true;
const AWS_CONFIG = {
    "region" : <region used for the deployment>,
    "API_ENDPOINT" : <URL for the prod stage of the API. Include /v1 at the end>,
    "APPNAME" : <name of the app used at deployment time> 
}
~~~
