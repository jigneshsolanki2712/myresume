# EC2 Instance Setup and Web App Deployment Guide

This guide provides step-by-step instructions for setting up an Amazon EC2 instance, updating it, installing Git, Apache2 web server, copying a web application, and accessing it via a web browser through ec2 public ip.
I
## Prerequisites

- An AWS account
- Basic knowledge of AWS services
- SSH client installed on your local machine

## Step-by-Step Instructions

1. **Sign in to AWS Console**: Go to the [AWS Management Console](https://aws.amazon.com/console/) and sign in to your account.

2. ## Create EC2 Instance**:
   - Navigate to the EC2 dashboard.
   - Click on "Launch Instance".
   - Choose "Ubuntu" as the AMI.
   - Select "t2.micro" as the instance type.
   - Follow the on-screen instructions to configure instance details, add storage, add tags, configure security groups, and review.
   - Launch the instance and select or create a new key pair to connect to the instance via SSH.

3. ## SSH into the Instance**:
   ```bash
   ssh -i path/to/your-key.pem ec2-user@your-instance-ip

4. ## Switch to Super User:
    ```bash
    sudo su

5. ## Update the Instance:
    ```bash
    apt-get update -y

6. ## Install Git:
    ```bash
    apt-get install git -y

7. ## Install Apache2 Web Server:
    ```bash
    apt-get install httpd -y

8. ## Start HTTPD Service:
    ```bash
    systemctl start httpd

9. ## Clone Web App:
    ```bash
    git clone https://github.com/asfaqshekh/updatedresume.git

10. ## Copy Files to Web Server Directory:
    ```bash
    cp index.html /var/www/html
    cp readme.md /var/www/html
    cp -r images /var/www/html
    cp -r documents /var/www/html

11. ## Verify Files:
    ```bash
    cd /var/www/html
    ls

12. ## Access Web App:

    Copy the public IP of your EC2 instance.
    Paste it into your web browser.
    You should see your HTML web app.

13. ## Additional Notes
    Ensure security group settings allow inbound traffic on port 80 (HTTP) to access the web app.
    Remember to terminate your EC2 instance when you're done to avoid unnecessary charges.
    Always follow best practices for AWS security and cost optimization.

14. ## Bingo! Enjoy the HTML WebApp.!!!!!!!