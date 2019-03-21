# AWS Space Invaders App

**DISCLAIMER:** *AWS Space Invaders App, and all complementary resources are provided without any guarantees, and you're not recommended to use it for production-grade workloads. The intention is to provide content to build and learn.*


## What is this?
This is a space invaders game with serverless back-end based on AWS services.

The purpose of this application is to act as content for learning and exercising concepts about developing highly scalable architectures for near real-time applications (NRTA).

Because of this goal, the application was ***intentionally*** implemented with common issues that newcomers to serverless development at AWS generally incur at when designing and developing highly scalable architectures. Some examples are:

* The definition of the partition key for the record sent to Kinesis Data Streams, and its side-effects when the back-end scales to multiple shards
* Consuming data from multiple shards
* Disregard multiple deliverables of the same record by Kinesis Data Streams
* How to structure the DynamoDb tables and avoid the limits for record size
* How to cope with closed session. Users can still send data to the back-end after the session being closed
* The security of the JWT token
* The performance of the consumer (Scoreboard web-application). The requirement states that we need to be able to observe in real-time the scoreboard positions but, do we really need to show all the scoreboard? Supposing that we have 1MM gamers, how does that work for a web app? Should we have two mechanisms, one for the top X gamers, and a search for the rest?

and more.

Some workshops leveraging Space Invaders, conducted by AWS Partners and AWS SAs, will touch these points, and about how to design it properly. 


## How to deploy

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