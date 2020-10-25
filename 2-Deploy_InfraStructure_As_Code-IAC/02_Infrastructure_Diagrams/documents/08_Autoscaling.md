#Glossary
**Autoscaling group**: It is a coherent group of Virtual Machines (EC2 instances) that allows running the exact number of VMs that are required to meet the demand/specification. The autoscaling group can automatically start or stop the servers (EC2 instances) according to the amount of incoming traffic. This behavior of the autoscaling group helps in two ways:

The consumer pays for the only duration of the servers when they were active.
The consumer doesn't have to worry about horizontal scaling of servers for a sudden peak in incoming traffic.
##Best Practice
* It is recommended that an autoscaling group **spans more than one availability zone, for reliability**.
* If we set the autoscaling group to run one resource, it will run that one resource in one of the availability zones.
* If there is a failure of that resource, the autoscaling group will shut it down in that availability zone and start that same resource in the other availability zone.

##Recommended Read
* [Read more about autoscaling group](https://docs.aws.amazon.com/autoscaling/ec2/userguide/AutoScalingGroup.html)