#Simple Queue Service
Amazon Simple Queue Service (SQS) is a fully managed message queuing service that allows you to integrate queuing functionality in your application. SQS offers two types of message queues: standard and FIFO.
#Features
* send messages
* store messages
* receive messages
#Tips
* The Simple Queue Service (SQS) is found under the Application Integration on the AWS Management Console.
* FIFO queues support up to 300 messages per second.
* FIFO queues guarantee the ordering of messages.
* Standard queues offer best-effort ordering but no guarantees.
* Standard queues deliver a message at least once, but occasionally more than one copy of a message is delivered.

####Resources
* [Amazon SQS Overview](https://aws.amazon.com/sqs/)
* [What is Amazon SQS](https://docs.aws.amazon.com/AWSSimpleQueueService/latest/SQSDeveloperGuide/welcome.html)