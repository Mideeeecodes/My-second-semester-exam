#### Cloud Engineering Second Semester Examination Project
## Provision a Linux Server
## NAME: ODDI, MARYAM OLAMIDE
## ALT SCHOOL ID: ALT/SOE/024/1831
### Provisioning the Server (Modern Approach)

## Launching an EC2 Instance
Firstly, Sign in to AWS and log in to the AWS Management Console.
Go to the EC2 dashboard or search for EC2
Secondly, launch instance by clicking "Launch Instance", choose name and tag,key pair and choose an application and OS: Images an Amazon Machine Image (AMI)- I used ubuntu.
Then, configure Instance: Choose instance type (in my case, i'm using the free tier), create security group under Firewall, allow SSH traffic from anywhere, it helps connect to your instance, allow HTTPS traffic from the internet, allow HTTP traffic from the internet, configure network settings, and add storage.
Finally, review and Launch: Review settings and launch the instance.

## Connecting to EC2 Instance
1. SSH: Use SSH to connect to your instance (e.g., ssh -i "key.pem" ec2-user@instance-public-ip).
2. EC2 Instance Connect: Use the EC2 Instance Connect feature in the AWS Management Console.

## Using EC2 Instance Connect
1. Update your ubuntu: To provide stability and performance, also new features and support. To do this; sudo apt update. Then install a web server (Nginx).

##  Webserver Setup (Next-Level Choices)- Nginx
1. Install Nginx: Nginx package is available in the Ubuntu repository, which is a collection of software packages that can be easily installed. To do this: 'sudo apt install ngnix' to install the ngnix server.
2. Type 'which ngnix' to confirm where the ngnix is; it should be in 'user/sbin/ngnix'.

## Find a domain(freedns.afraid.com)
1. Create an account on freedns
2. Sign up and create a subdomain on freedns. Then you go to your EC2 instance(the one that is already running) to copy the public ip address and add it to the subdomain on the freedns.

## Dynamic Landing Page (Beyond Static HTML)
1. Create your personalized landing page, (your name & role, project title, a short pitch, a professional bio: skills, past projects, education) with optional enhancements like CSS animations or a lightweight framework (Tailwind). 
2. After that, push to github.

## Clone Your Github Repository
1. git clone [MyLink](https://github.com/Mideeeecodes/My-second-semester-exam.git)
2. Type 'ls' to check if you cloned the right link then you should see it (My-second-semester-exam)
3. Then you move everything in 'My-second-semester-exam' to where default nginx configuration is using 'mv My-second-semester-exam /* /var/www/html/'
4. Copy the public ip of the EC2 and paste in the browser to check if your website is up and running.

  ## Install the Nginx plugin for Certbot
 Install Certbot: it is popular tool for obtaining and managing SSL/TLS certificates from Let's Encrypt.Certbot automates certificate issuance, renewal, and installation. By using Certbot, you can easily obtain and manage SSL certificates for your Nginx server, ensuring a secure connection for your users.
  To install : 'sudo apt install certbot -y'.

Plugin is used for:
1. Nginx integration: The plugin integrates Certbot with Nginx allowing for automated certificate issuance and installation.
2. Configuration management: The plugin can automatically configure Nginx to use the obtained SSL certificates.

## Benefits of using the plugin
1. Streamlined certificate management: The plugin simplifies the process of obtaining and installing SSL certificates for Nginx.
2. Automated configuration: The plugin can automatically update Nginx configurations to use the obtained certificates.
## To install:
'Sudo apt install python3-certbot-nginx' is used to install the Nginx plugin for Certbot and 
'Sudo certbot --nginx' to obtain and install certificate
'Sudo certbot --nginx'~ will ask you for your email address(for urgent renewal and security notice) input it then proceed. They will ask for domain that you will like for certificate.
Then a certificate will be deployed to you successfully.
You will get a message saying you have enabled HTTPS on your HTTP 

##IMAGES OF THE RENDERED PAGE WITH THE DOMAIN NAME
![image1](/images/image1.png)
![Image2](/images/image2.png)
![Image3](/images/image3.png)
![Image4](/images/image4.png)


##IMAGE WITH PULIC IP ADDRESS WHERE THE PAGE IS HOSTED
[Imag5](/images/Screenshot%202025-06-14%20142549.png)








