#Setup AWS Free-Tier Account

In this hands-on exercise, you will sign-up for an AWS free-tier account so that you can gain access to the AWS platform, products, and services. The free-tier account has three levels of service: 12-month free, always free, and free trial.

##Prerequisites:
* Credit card
* Valid email address
* Phone number (used during sign up for validation)
* Virtual Multi-Factor Authentication (MFA) application, such as, Google Authenticator, Authy 2-Factor Authentication, or Authenticator installed on your mobile phone
##Topics Covered:
By the end of this lab, you will be able to:

* Sign into your AWS account in a secure fashion using MFA.

##Steps:
1. ####Sign up

    * Navigate to https://aws.amazon.com/free/
    *  Click on the “Create a Free Account” button
    * Enter your email address, password, and a name for your account. Important: Be sure to enter your email address correctly or you will not have access to your account.
    * Create a “Personal” account and fill out the contact information.
    * Enter your payment information. Important: You will not be charged unless your usage exceeds the free-tier limits.
    * Verify your account by phone.
    * Select your support plan. Important: Select the “Free” plan.
    * Finish the account setup.

2. ####Setup Multi-Factor Authentication (MFA)
    MFA adds an extra-layer of security on your account, which requires a username, password, and a security key retrieved from the MFA application on your mobile phone to login.

    * Sign in to your account using the credentials (e.g. username and password) that you created in Step 1.
    * In the “AWS Services” text box, type “IAM”.
    * Select “IAM”.
    * On the dashboard, select “Activate MFA on your root account”
    * Click on “Manage MFA”
    *  Follow the steps to setup “a Virtual MFA device”