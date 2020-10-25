#Deciding Access Privileges within AWS
##Programmatic Access
In the AWS console, choose **"programmatic access."** This allows us to use code to interact with AWS, instead of relying on mouse clicking in the console web pages.

##Administrator Access
For IAM access, choose **“administrator access.”** This is just for initial setup of your account. Afterwards, you’ll want to limit access to only what you need.

##Dev and Prod user accounts
In practice, Dev and DevOps members may have separate user accounts for the dev environment as opposed to the production environment. This makes it easier for developers by giving them wider privileges in the dev environment that would normally only be reserved for DevOps members in the production environment.

##Access Key ID and Secret Access Keys
Remember not to save these in your code or to check into any repositories. Keep these private to you.

