# Load Balancer Web Page link

http://udaha-webap-cpjpzoqpd8k7-1406778340.us-west-2.elb.amazonaws.com/

# High Availability Web App Using AWS CloudFormation

This is a realistic scenario where we deploy an application (Apache Web Server) and also pick up code (JavaScript and HTML) from S3 Storage and deploy it in the appropriate folder on the web server.

In this project, we’ll deploy web servers for a highly available web app using CloudFormation. we will write the code that creates and deploys the infrastructure and application for an Instagram-like app from the ground up. we will begin with deploying the networking components, followed by servers, security roles and software. we’ll do it exactly as it’s done on the job - following best practices and scripting as much as possible.

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

3- Servers will need unrestricted internet access for the outbound.

4- Load balancer should allow all public traffic (0.0.0.0/0) on port 80 inbound.

5- Load balancer will only be using port 80 to reach the internal servers (outbound).

6- The application needs to be deployed into private subnets.

7- Load Balancer located in a public subnet.

8- One of the output exports of the CloudFormation script should be the public URL of the LoadBalancer.

9- Bonus points if you add http:// in front of the load balancer DNS Name in the output, for convenience.


## Other Considerations:

1- 1st deploy your servers with an SSH Key into Public subnets while you are creating the script. Once done correctly, move them to the private subnets and remove the SSH Key from your Launch Configuration.

2- Test directly, without the load balancer. Once you are confident that your server is behaving correctly, increase the instance count.

3- Need the SSH port open (port 22) for access, in case of the instances troubleshooting.

4- Log information for UserData scripts is located in this file: cloud-init-output.log under the folder: /var/log.

5- We should be able to destroy the entire infrastructure and build it back up without any manual steps required, other than running the CloudFormation script.

6- The provided UserData script should help us install all the required dependencies.

7- We have to decide which values should be parameters and which will be hard-coded in the script.

8- Extra mile, set up a bastion host to allow you to SSH into your private subnet servers. This bastion host would be on a Public Subnet with port 22 open only to your home IP address, and it would need to have the private key that you use to access the other servers.

## Supporting links

1- Starter code:

 https://video.udacity-data.com/topher/2019/July/5d391e8b_final-project-starter/final-project-starter.yml

2- Project specification:

https://review.udacity.com/#!/rubrics/2556/view
