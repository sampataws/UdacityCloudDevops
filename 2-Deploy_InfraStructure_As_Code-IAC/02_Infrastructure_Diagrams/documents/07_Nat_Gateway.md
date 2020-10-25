#Network Address Translation (NAT) Gateway
It provides outbound-only internet gateway for private services to access the internet. This keeps the private service protected from inbound connections, but allows it to connect to the internet in order to perform functions such as downloading software updates. The NAT gateway serves as an intermediary to take a private resource’s request, connect to the internet, and then relay the response back to the private resource without exposing that private resource’s IP address to the public.

**Note**: Place NAT Gateways inside the **public** subnets and not the private subnets. NAT gateways need to be in the public subnet so that they can communicate with the public internet, and handle requests from resources that are in a private subnet.

####Recommended Read
* [Read more about Network Address Translation (NAT) Gateway](https://docs.aws.amazon.com/vpc/latest/userguide/vpc-nat-gateway.html)