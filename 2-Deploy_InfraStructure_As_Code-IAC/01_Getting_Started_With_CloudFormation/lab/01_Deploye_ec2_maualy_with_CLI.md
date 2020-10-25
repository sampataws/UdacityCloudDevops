##Manually deploy an EC2 Instance for use with the CLI Tool.
We have installed and configured the AWS CLI to do our work for this course. However, there’s an alternative.

Go ahead and create an EC2 Instance that you can SSH into (or Remote Desktop, if you prefer Windows). Do this manually, in the console. Be sure to limit access to your IP address only, using Security Groups.

Once the instance is running, create an IAM Role with Admin access to your account, associate the role to your EC2 and install the AWS CLI on it.

The CLI tool, in this case, will pick up the credentials from the role and won’t need hard-coded credentials

##Exercise Solution
We strongly recommend you to solve the exercise on your own. If stuck, you may see the lesson-wise solution available in this [GitHub repository](https://github.com/udacity/nd9991-c2-Infrastructure-as-Code-v1-Exercises_Solution)