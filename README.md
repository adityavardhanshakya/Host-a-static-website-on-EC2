# How to Host a Static Website in Amazon Web Services using EC2 Instance and GitHub Repository

This repository provides a step-by-step guide on how to host a static website in Amazon Web Services (AWS) using an EC2 instance and a GitHub repository. By following these instructions, you will be able to deploy your static website and make it accessible to the world.

## Prerequisites
Before getting started, make sure you have the following:

1. An AWS account with appropriate permissions to create and manage EC2 instances.
2. A GitHub account and a repository containing your static website's code.
3. Basic knowledge of AWS services, including EC2, Amazon Machine Images (AMI), Security Groups, and Elastic IP.

## Steps to Host a Static Website

### 1. Launch an EC2 Instance

To host your static website, you need to launch an EC2 instance in AWS. Follow these steps to create and configure the instance:

1. Sign in to your AWS Management Console.
2. Open the EC2 dashboard.
3. Click on "Launch Instance" and select an appropriate AMI, such as Amazon Linux 2.
4. Choose an instance type, storage, and other configuration settings.
5. Configure the security group to allow inbound traffic on port 80 (HTTP) and 22 (SSH).
6. Launch the instance and download the private key file.

### 2. Connect to the EC2 Instance

To connect to the EC2 instance, follow these steps:

1. Locate the public IP address of your EC2 instance.
2. Open a terminal or command prompt on your local machine.
3. Use the following command to connect to your EC2 instance:

```bash
ssh -i /path/to/private/key.pem ec2-user@public-ip-address
```

### 3. Install and Configure Web Server

To serve your static website, you need to install a web server on your EC2 instance. Here's how:

1. Connect to your EC2 instance as described in the previous step.
2. Install a web server like Apache or Nginx. For Apache, use the following command:

```bash
sudo yum install httpd
```

3. Start the web server:

```bash
sudo service httpd start
```

### 4. Clone Your GitHub Repository

Next, you need to clone your GitHub repository to the EC2 instance:

1. Connect to your EC2 instance.
2. Install Git if not already installed:

```bash
sudo yum install git
```

3. Clone your GitHub repository:

```bash
git clone https://github.com/your-username/your-repository.git
```

### 5. Configure Website Content

After cloning the repository, configure the web server to serve your static website:

1. Move the contents of your repository to the appropriate web server directory. For Apache, use the following command:

```bash
sudo cp -R your-repository/* /var/www/html/
```

### 6. Access Your Website

Your static website should now be accessible at the public IP address of your EC2 instance. Simply enter the IP address in a web browser to view your website.

### 7. Assign an Elastic IP (Optional)

By default, the public IP address of your EC2 instance may change if you stop and start the instance. If you want a fixed IP address for your website, you can assign an Elastic IP:

1. Go to the EC2 dashboard.
2. Select "Elastic IPs" from the sidebar menu.
3. Click "Allocate new address" and then "Allocate".
4. Select the newly allocated Elastic IP and choose "Actions" > "Associate IP address".
5. Associate the Elastic IP with your EC2 instance.


# Thank you so much ! Hit a like like button if you like our content @vardhana3098@gmail.com
