# deploy-react-to-aws-scripts

The script file must be placed in the top level of the git repository where you have your react project.
The localscript can then be run from your local machine using the command 'bash localscript'.
Ensure you already have an AWS account, and created a User with access keys which will be needed to configure the AWS CLI when you run the localscript.

The localscript will install the AWS command line interface if it is not already installed, and prompt you to configure the AWS CLI entering the access keys. The region has defaulted to ap-southeast-2 (Sydney). When it asks for output format, 'json' should suffice.
A Key Pair will be created with the name MyKeyPair if it does not already exist, and the pem file will be placed in the current directory. This key pair will be needed if you want to ssh into the AWS instance.
Then the script will initialise 1 t2-micro ec2 instance, and the rest is history :).
