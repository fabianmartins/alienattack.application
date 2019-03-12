# AWS Space Invaders App

**DISCLAIMER:** AWS Space Invaders App, and all complementary resources are provided without any guarantees, and you're not recommended to use it for production-grade workloads. The intention is to provide content to build and learn.


## What is this?
This is a space invaders game with serverless back-end based on AWS.

Before running it, you need to deploy the back-end, which is in the project [Space Invaders CDK](https://github.com/fabianmartins/spaceinvaders.cdk).

After deploying the back-end, you need to update the file `./resources/js/aws-config` with the required data.

~~~
const DEBUG = true;
const AWS_CONFIG = {
    "region" : <region used for the deployment>,
    "API_ENDPOINT" : <URL for the prod stage of the API. Include /v1 at the end>,
    "APPNAME" : <name of the app used at deployment time> 
}
~~~