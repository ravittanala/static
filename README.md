# static
Jenkins (BlueOcean)-Pipeline:
    This Project demonstrates the Creation of a Jenkins pipeline (Part of CI) which contains different stages and each individual stage will perform different activities and at the end the file will be uploaded to an AWS S3 bucket.

AWS Setup:

 1) A new user with EC2 and S3 access is created that is not the root/admin user in AWS.
 2) An Ubuntu 18.04 t2.micro is launched and can be accessed via SSH using the PEM file.
 3) Create a S3 bucket with static web hosting.
 
Jenkins Setup:

 1) Login to EC2 instance and install Jenkins and tidy.
 2) Install the necessary plug-ins along with Blue Ocean.
 3) The GitHub repository is added and shows in the BlueOcean dashboard.
 4) Add the AWS credentials (Access Key and Secret Key) to the jenkins Credentials.
 
Creating the Pipe line:

 1) Creating the pipeline with a simple stage called Build.
 2) Edit the pipeline and add the Linter Stage to the pipeline and Save which will validate the index.html file and post the status.
 3) Add the "Upload to AWS" stage and provide the aws credentials, file name and S3 bucket details.
 4) Run the Pipe line.
 
The index.html would be moved to the mentioned S3 bucket and we can see the content of the file using the below url,

https://jenkinsblueocean.s3.us-east-2.amazonaws.com/index.html
 
  
  
  
  


