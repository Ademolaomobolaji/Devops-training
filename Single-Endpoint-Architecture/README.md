# Single Endpoint Architecture for EC2 and S3 Services

## Project Goals and Learning Outcomes
- By Completeing this project, You'll know 

-Mastered the Integration of EC2 and S3 for applications, Balancing compute and storage needs.
- Gained practical experience in setting up a reverse proxy on EC2 to Facilitate unified access to both EC2 and S3 resources.
- Learned the seamless resource integration in building scalable and secure solutions.


### Setting up EC2 Instance
- login AWS console with John's account (User with priviledge to run EC2 services)
- Launch Ubuntu Instance 
- Assing a static IP:Associate an elastic IP address with your instance to ensure it retains the same Public Address.

### Create an S3 Bucket
- Log in to Mary's (it has S3 permissions)
- Create a new bucket and give it a name.
- Create a new object inside the bucket.


### Configure a web Server as a reverse proxy
- Install Nginx web server on your Ec2

- Run- Sudo apt update -y && Sudo apt install nginx -y

Configure the web server: Configure to server your S3 app directly and to forward request to your S3 bucket.