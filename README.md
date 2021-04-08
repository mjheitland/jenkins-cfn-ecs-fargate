# Deploying a production-ready Jenkins Server on ECS/Fargate using CloudFormation

[Tutorial](https://tomgregory.com/deploy-jenkins-into-aws-ecs/)

## Input Parameters for CFN Stack
1. JenkinsDockerImage: Docker image used in the ECS task definition. Override the default to use a custom image (mandatory). Provision the required resources for blog post example 'Deploying Jenkins to ECS'. Wait for creation to complete before testing. Default = jenkins/jenkins:lts

2. CertificateArn: ARN of an existing certificate which will be attached to the ALB created by the stack, to serve HTTPS traffic (mandatory).
