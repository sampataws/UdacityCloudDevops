#Simple Notification Service
Amazon Simple Notification Service (or SNS) is a cloud service that allows you to send notifications to the users of your applications. SNS allows you to decouple the notification logic from being embedded in your applications and allows notifications to be published to a large number of subscribers.
#Features
* SNS uses a publish/subscribe model.
* SNS can publish messages to Amazon SQS queues, AWS Lambda functions, and HTTP/S webhooks.
#Tips
* SNS is found under the Application Integration section on the AWS Management Console.
* SNS Topic names are limited to 256 characters.
* A notification can contain only one message.

**Resources**

* [Amazon SNS Overview](https://aws.amazon.com/sns/)
* [What is Amazon SNS](https://docs.aws.amazon.com/sns/latest/dg/welcome.html)