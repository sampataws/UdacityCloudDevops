##A. What is an AWS UserData script?
A UserData script is a series of commands that you use to properly configure your server to run your application.

This is where you do things such as:

* Fetch credentials
* Set Environment Variables ( ENV=PROD, for example )
* Download and Install libraries
* Get your source files or binaries from a storage location, such as S3

##When should you use it?
If you want to run your application in a plain out-of-the-box Linux or Window server, you'll use the UserData script to do all the necessary configurations. **You don't need it if you are using a Virtual Machine Image ( AMI ) that already has everything installed**.

##B. Verification and troubleshooting
The best way to create and verify a UserData script is to run each command manually and verify everything works as expected. If you run yours and it fails, you should login to the server and check the logs that can be found here: ```/var/log/cloud-init-output.log```. For Windows: ```C:\ProgramData\Amazon\EC2-Windows\Launch\Log\UserdataExecution.log```

###Difference between UserData on Windows and Linux
On Windows, you have the option of PowerShell:

```xml
<powershell>
$file = $env:SystemRoot + "\Temp\" + (Get-Date).ToString("MM-dd-yy-hh-mm")
New-Item $file -ItemType file
</powershell>
```

Or more traditional Batch scripts:

```xml
<script>
echo Current date and time >> %SystemRoot%\Temp\test.log
echo %DATE% %TIME% >> %SystemRoot%\Temp\test.log
</script>
```

For Linux, follow the included example.

##C. Auto Scaling Concepts
###1. Scaling Policy
A Scaling Policy is the criteria used to decide when to Add or Remove Servers from your Auto Scaling Group. Running the servers 24 hours a day costs money. So, It's best to have criteria to choose to turn those servers off when they are not needed and then turn them back on when there is demand.

This is achieved using a Scaling Policy. For example, you could create a CloudWatch Alarm with a custom metric that counts the number of web visitors in the last 2 hours, if the number is less than 100, for example, perhaps a single server is enough. This will be a trigger to Scale Down if there is more than one server running at the time.

###2. Launch Configuration
Think of a Launch Configuration as a template or a recipe. You are instructing the Auto Scaling service HOW to run your web application. For example: My application requires 2GB RAM , 4 vCPUs, 10GB of Disk Space, The Java runtime version 8 Or NodeJS 10.0, for example. All this on top of a standard distribution of Linux or Windows Read more about Launch Configuration.

Once an Auto Scaling group knows how to launch new copies of your application, then the process of scaling up and down can take place.

###3. Load Balancer
While a load balancer is not exactly a part of Auto Scaling but it helps answer the question: "If I am running a web application in 20 different servers, how do I setup a single point of entry that guarantees an even workload distribution across all 20 servers?" The answer is: with a Load Balancer.

A load balancer allows you to reduce your Auto Scaling down to 1 server at night, when very few people are using your Web Application and then Scale up to 10 or more servers during the day, when hundreds or thousands may be using it. The user doesn't experience any difference in availing the services due to auto-scaling.

####Further reading
The [AWS Frequently Asked Questions](https://aws.amazon.com/autoscaling/faqs/) (FAQs) is a great resource to master the finer details of scaling servers