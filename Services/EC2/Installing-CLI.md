# Installing AWS CLI on Windows

Once the installation is done, confirm the same by running the `aws --version` command.

## AWS CLI for Windows

https://docs.aws.amazon.com/cli/latest/userguide/install-windows.html#install-msi-on-windows


## AWS CLI for Ubuntu
https://docs.aws.amazon.com/cli/latest/userguide/install-linux.html

1. Create an Ubuntu EC2 instance and execute the below commands.
    >sudo apt-get update\
    >sudo apt-get install python2.7 python-pip -y\
    >pip install awscli --upgrade\
    >export PATH="$PATH:/home/ubuntu/.local/bin/"\

## Generating the Access Keys

1. Generate the credentials from the below link
https://console.aws.amazon.com/iam/home?region=us-east-1#/security_credential
    - Click on `Continue with Security Credentials`
    - Click on `Access keys (access key ID and secret access key)`.
    - Click on `Create New Access Key`.
    - Note down the keys.

1. Run the `aws configure` command to specify the region (us-east-1 for North Virginia) and the keys. For the default output format leave blank.

## Commands to create AWS resources

1. Create the Security Group and open port 22.
    >aws ec2 create-security-group --group-name ssh-access --description "allow ssh"
    >aws ec2 authorize-security-group-ingress --group-name ssh-access --protocol tcp --port 22 --cidr 0.0.0.0/0

1. Get the subnets
    >aws ec2 describe-subnetsec2

1. Terminate the instance
    >aws ec2 terminate-instances --instance-ids i-032154634c23e4868

# Further Reading

CLI Reference Guide\
https://docs.aws.amazon.com/cli/latest/reference/ (v1)
https://awscli.amazonaws.com/v2/documentation/api/latest/index.html (v2)

Configure Auto Completion with the CLI
https://docs.aws.amazon.com/cli/latest/userguide/cli-configure-completion.html

s3 vs s3api commands\
https://aws.amazon.com/blogs/developer/leveraging-the-s3-and-s3api-commands/

AWS CLI v1 vs v2\
https://www.youtube.com/watch?v=U5y7JI_mHk8