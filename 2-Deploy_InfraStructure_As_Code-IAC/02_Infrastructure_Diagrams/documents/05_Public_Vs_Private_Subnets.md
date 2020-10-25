#Subnets
* A subnet is a subset of the overall VPC network and it only exists in a single availability zone, unlike its parent network, the VPC.
* A subnet contains resources, and can be assigned access rights that apply to all resources within that subnet.
* Subnets can be public or private. Public subnets are accessible to external users. Private subnets are only accessed internally by other resources within your cloud container.

##Use IP addresses for routing traffic
* Use IP addresses as the “keys” for routing traffic. We can route traffic to stay within the VPC, or within a particular subnet, for security reasons.
* For example, a database or any sensitive data will be placed in a private subnet. A public server, like a web server, can be placed in a public subnet. Routing rules applied to a subnet allow us to define access to all resources placed inside that subnet.