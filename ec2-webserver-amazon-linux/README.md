# EC2 Web Server on Amazon Linux

## What I Built
Launched an Amazon EC2 instance running Amazon Linux. Installed and configured Apache (httpd) web server via User Data. Created and stored a reusable Amazon Machine Image (AMI).

## Architecture
- **EC2 Instance:** Amazon Linux 2
- **Security Groups:** Allowed SSH (22), HTTP (80), and HTTPS (443)
- **User Data Script:** Automated Apache install and start
- **AMI:** Created snapshot for scaling or replication

## Steps
1. Launch EC2 instance (Amazon Linux 2).
2. Configure Security Group: allow SSH (22), HTTP (80), HTTPS (443).
3. Add User Data script:

   ```bash
   #!/bin/bash
   yum update -y
   yum install -y httpd
   systemctl start httpd
   systemctl enable httpd
   echo "Hello from FabCloudTech EC2 Web Server" > /var/www/html/index.html
## Cleanup
- Terminate the EC2 instance when finished.
- Deregister and delete the AMI if not needed.
- Delete associated snapshots and security groups to avoid charges.

## Notes
- Practice lab from AWS Cloud Practitioner course. 
- Demonstrated launching EC2, configuring security groups, using User Data, and creating AMIs. 
- Verified web server output on public IP. 
