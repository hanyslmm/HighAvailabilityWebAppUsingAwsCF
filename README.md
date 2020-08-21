# High Availability Web App Using AWS CloudFormation

This is a realistic scenario where we deploy an application (Apache Web Server) and also pick up code (JavaScript and HTML) from S3 Storage and deploy it in the appropriate folder on the web server.

## There will be two parts to this project:

1- Develop a diagram that is a visual aid to understand the CloudFormation script.

2- Interpret the instructions & diagram to create a matching CloudFormation script.


## Task description:

Your company is creating an Instagram clone called Udagram. Developers pushed the latest version of their code in a zip file located in a public S3 Bucket.

You have been tasked with deploying the application, along with the necessary supporting software into its matching infrastructure.

This needs to be done in an automated fashion so that the infrastructure can be discarded as soon as the testing team finishes their tests and gathers their results.

## Auto-scaling servers specification

1- 4 servers (two in each private subnets)

2- 2 vCPUs & 4GB of RAM

3- Ubuntu 18

4- 10GB Disk spcace

## Security Groups and Roles

1- Create an IAM Role that allows your instances to use the S3 Service.

2- Servers will need HTTP Port: 80 inbound port open (will use it with the Load Balancer and the Load Balancer Health Check).

3- Servers will need unrestricted internet access for the outboun.

4- Load balancer should allow all public traffic (0.0.0.0/0) on port 80 inbound.

5- Load balancer will only be using port 80 to reach the internal servers (outbound).

6- The application needs to be deployed into private subnets.

7- Load Balancer located in a public subnet.

8- One of the output exports of the CloudFormation script should be the public URL of the LoadBalancer.

9- Bonus points if you add http:// in front of the load balancer DNS Name in the output, for convenience.
