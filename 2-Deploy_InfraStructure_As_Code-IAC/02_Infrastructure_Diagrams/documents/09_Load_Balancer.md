#Load Balancer
* A load balancer takes incoming traffic and distributes it to two or more resources. For example, it can take inbound user requests to access your website, and it can distribute the requests evenly among two or more servers.
* Without a load balancer, having public-facing servers in more than one AZ would mean that users would have to use a different URL to reach each of the AZs. This can be impractical compared to just a single URL.
* **Good practice** - Assume we have a set of web-servers in private subnet(s). Then, we must have a Load Balancer that would access our web-servers. These web-servers, in turn, would access the backend database.
##AWS - Elastic Load Balancing
We recommend you to read about three types of load balancing offered by AWS at different layers of networking protocol:

1. [Classic load balancer](https://docs.aws.amazon.com/elasticloadbalancing/latest/classic/introduction.html)
2. [Application load balancer](https://docs.aws.amazon.com/elasticloadbalancing/latest/application/introduction.html)
3. [Network Load balancer](https://docs.aws.amazon.com/elasticloadbalancing/latest/network/introduction.html)