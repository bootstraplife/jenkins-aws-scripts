# jenkins-aws-scripts

This repo is if you want to automate the creation of a CICD pipeline on an AWS cloud instance.

The localscript is all you need in your local machine to run. It will create an EC2 AWS instance and pull the Docker Jenkins image, and run the image. The login is user:admin, pw:admin

The Jenkinsfile needs to be placed in the top of the directory of your Git repo.

The Dockerfile will allow you to recreate the docker image used locally if you want to make any changes.


If you don't have the AWS CLI installed yet then fyi below

The localscript will install the AWS command line interface if it is not already installed, and prompt you to configure the AWS CLI entering the access keys. The region has defaulted to ap-southeast-2 (Sydney). When it asks for output format, 'json' should suffice.
A Key Pair will be created with the name MyKeyPair if it does not already exist, and the pem file will be placed in the current directory. This key pair will be needed if you want to ssh into the AWS instance.
Then the script will initialise 1 t2-micro ec2 instance.
