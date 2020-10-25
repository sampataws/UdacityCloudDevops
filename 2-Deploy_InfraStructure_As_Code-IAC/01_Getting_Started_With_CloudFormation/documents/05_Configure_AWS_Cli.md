##Configuring the AWS Command Line Interface (CLI)
* Download and install the [AWS CLI tool](https://aws.amazon.com/cli/).
* In the terminal, type ```aws --version```: this verifies that you have the AWS CLI tool.
* To set up your AWS CLI, type ```aws configure``` in the terminal. Next when prompted for the AWS Access Key ID, paste in your ```Secret access key```.
* Region: Please use ```us-west-2```, even if you’re living closer to another available region.
##Verifying your Setup
* One way to check if your AWS CLI is set up properly is to try a command. You can try listing your S3 buckets:```aws s3 ls``` . **This will be blank if you have no S3 buckets.** However, if you have no error message, then you’ve verified that your user has API access to communicate with AWS.
* Note that each user can have up to 2 access keys at the same time.
##Additional Access Keys
Note that each user can have up to 2 access keys at the same time.

##Why Making Keys Inactive is a Better Choice
You may make your access key temporarily inactive rather than destroying it and creating a new one. This may be helpful if you want to stop an automated process that uses that key (for example, a CI/CD process).