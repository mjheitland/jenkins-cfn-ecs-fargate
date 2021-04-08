# Deploying a production-ready Jenkins Server on ECS/Fargate using CloudFormation

[Tutorial](https://tomgregory.com/deploy-jenkins-into-aws-ecs/)

## Input Parameters for CFN Stack
1. JenkinsDockerImage: Docker image used in the ECS task definition. Override the default to use a custom image (mandatory). Provision the required resources for blog post example 'Deploying Jenkins to ECS'. Wait for creation to complete before testing. Default = jenkins/jenkins:lts

2. CertificateArn: ARN of an existing certificate which will be attached to the ALB created by the stack, to serve HTTPS traffic (mandatory). Default = arn:aws:acm:eu-west-1:094033154904:certificate/f82b38ad-5ff1-4e92-b6f9-fa4e0752cde9

## Adding ALB url to Route53
1. Add a CNAME record jenkins.r53.heitland-it.de with the url of ALB (get it from stack outputs, e.g. jenki-LoadB-11ZVBSDN0DA8P-503870070.eu-west-1.elb.amazonaws.com)

## Testing
Turn off any VPN, otherwise Route53 as our AWS DNS won't resolve the url!

1. https://jenkins.r53.heitland-it.de  
2. Enter admin password found in cloudwatch log
