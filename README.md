# Deploy-WebApplication-on-AWS-S3Create S3 bucket

Object Ownership must be ACL enabled(i.e accessible publicly if given public access)

Disable blocked public address

Bucket created successfully! 

Upload the .zip file in the s3 bucket
 
Give it public access with ACL
 
Copy the link of the zip file in the s3 bucket( we will use it later)

Create EC2 Instance enabled with HTTP & HTTPS protocols(Ports:22,443,80)
 
 
Create security group & download the .ppk file
 
After initializing the EC2 Instance, we will have to connect it to the VM.
For this we have three methods:
1. We will use the PuTTY to convert .pem file(The key which we downloaded while creating the instance) to .ppk and launch it on our local  System/machine
2. If we have downloaded the .ppk file then we can directly initialize the VM on our local Machine/System.
3. We will directly connect to the VM through the AWS platform

I have used the 2nd method.
 
In the VM run the following commands top deploy the webpage on the AWS Cloud:
1. sudo su
2. yum update -y
3. yum install -y httpd
4. cd /var/www/html
5. wget s3_bucket_zip_file_link
6. ls
7. unzip Website.zip
8. cp -r Website/* /var/www/html/
9. rm -rf Website Website.zip
10. systemctl enable httpd
11. systemctl start httpd
12. systemctl status httpd
Copy the iPV4 address of the EC2 Instance

We have Successfully Deployed the Web Application on AWS Cloud!
