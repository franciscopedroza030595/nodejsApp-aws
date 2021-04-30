## Express App On AWS 

A dockerize App to get, update and post data using Express. Uploaded on AWS ECR , using ECS setting AWS Fargate and a load balancer.

### Dockerfile is in charge to run all the necessary commands to deploy the app on a cloud container service
```

FROM node:14

WORKDIR /app

ENV NODE_ENV production

COPY package*.json ./

RUN npm install

COPY . .

RUN npm install -g pm2

EXPOSE 3000

CMD ["pm2-runtime", "index.js"]


```

#### In AWS create a new repository on service Elastic Cointer Registry, upload the project and follow the AWS step by step to register the Docker container.

![image](https://user-images.githubusercontent.com/47983522/116721757-4eb23f80-a9a3-11eb-8e19-14f0c8d63e2e.png)


#### Create a cluster in AWS ECS(Elastic Container Services), using AWS fargate(a serverless informatic motor) for run task requests of the container registered previously.

![image](https://user-images.githubusercontent.com/47983522/116722760-6e963300-a9a4-11eb-99ce-594421acd538.png)

