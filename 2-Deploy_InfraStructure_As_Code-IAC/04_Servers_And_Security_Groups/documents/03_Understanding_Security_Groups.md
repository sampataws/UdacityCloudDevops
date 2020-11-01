#Security Groups
The following is the syntax required to create a ```SecurityGroup```:

```yaml
Type: AWS::EC2::SecurityGroup
Properties: 
  GroupDescription: String
  GroupName: String
  SecurityGroupEgress: 
    - Egress
  SecurityGroupIngress: 
    - Ingress
  Tags: 
    - Tag
  VpcId: String
```

Although they are not required, the ```SecurityGroupEgress``` and ```SecurityGroupIngress``` property rules are the most critical to the ```SecurityGroup``` as it defines where the traffic will go. While ```SecurityGroupEgress``` defines outbound traffic, ```SecurityGroupIngress``` defines the inbound traffic.

###Ingress rules and egress rules
* Ingress rules are for inbound traffic, and egress rules are for outbound traffic.
* Ingress rules restrict or allow traffic trying to reach our resources on specific ports.
* Egress rules restrict or allow traffic originating from our server -- typically we are ok allowing all outbound traffic without restrictions as this doesn’t pose a risk for a security breach.

####Resources
* [Security Groups Resource](https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/aws-properties-ec2-security-group.html)