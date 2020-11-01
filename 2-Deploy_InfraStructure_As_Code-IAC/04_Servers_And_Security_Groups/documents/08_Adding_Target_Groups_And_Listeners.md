##Relationship between Target Groups and Auto Scaling groups.
A Load Balancer is a device that simply forwards traffic, evenly across a group of servers, known as a Target Group.

The problem is, we can’t specifically name those servers, because if they are part of an Auto Scaling group, this means that they can come and go as demand for your application increases or decreases.

The way around this is, using the ```TargetGroupARNs``` property of the Auto Scaling group, we can automatically associate any new servers and remove discarded servers from the Target group automatically by simply including the Resource Name (ARN) of our Load Balancer’s target group in this property of our Auto Scaling Group. This way, the Load Balancer will always know where to send the traffic.

The following is the required syntax for ```Load Balancer``` and ```Listener```
```yaml
 WebAppLB:
    Type: AWS::ElasticLoadBalancingV2::LoadBalancer
    Properties:
      Subnets:
      - Fn::ImportValue: !Sub "${EnvironmentName}-PUB1-SN"
      - Fn::ImportValue: !Sub "${EnvironmentName}-PUB2-SN"
      SecurityGroups:
      - Ref: LBSecGroup
  Listener:
    Type: AWS::ElasticLoadBalancingV2::Listener
    Properties:
      DefaultActions:
      - Type: forward
        TargetGroupArn:
          Ref: WebAppTargetGroup
      LoadBalancerArn:
        Ref: WebAppLB
      Port: '80'
      Protocol: HTTP
  ALBListenerRule:
      Type: AWS::ElasticLoadBalancingV2::ListenerRule
      Properties:
        Actions:
        - Type: forward
          TargetGroupArn: !Ref 'WebAppTargetGroup'
        Conditions:
        - Field: path-pattern
          Values: [/]
        ListenerArn: !Ref 'Listener'
        Priority: 1
```

The following is the required syntax for ```TargetGroup```:

```yaml
Type: AWS::ElasticLoadBalancingV2::TargetGroup
Properties: 
  HealthCheckEnabled: Boolean
  HealthCheckIntervalSeconds: Integer
  HealthCheckPath: String
  HealthCheckPort: String
  HealthCheckProtocol: String
  HealthCheckTimeoutSeconds: Integer
  HealthyThresholdCount: Integer
  Matcher: 
    Matcher
  Name: String
  Port: Integer
  Protocol: String
  Tags: 
    - Tag
  TargetGroupAttributes: 
    - TargetGroupAttribute
  TargetType: String
  Targets: 
    - TargetDescription
  UnhealthyThresholdCount: Integer
  VpcId: String
```

```Health Checks``` are the requests your ```Application Load Balancer``` sends to its registered targets. These periodic requests test the status of these targets. You can see us defining our ```Health Check``` properties in the example below:

```yaml
 WebAppTargetGroup:
    Type: AWS::ElasticLoadBalancingV2::TargetGroup
    Properties:
      HealthCheckIntervalSeconds: 35
      HealthCheckPath: /
      HealthCheckProtocol: HTTP
      HealthCheckTimeoutSeconds: 30
      HealthyThresholdCount: 2
      Port: 80
      Protocol: HTTP
      UnhealthyThresholdCount: 5
      VpcId: 
        Fn::ImportValue:
          Fn::Sub: "${EnvironmentName}-VPCID"
```

###In the above example we specify the following:

* The port where our targets receive traffic - ```Port: 80```
* The protocol the load balancer uses when performing health checks on targets - ```HealthCheckProtocol: HTTP```
* The time it takes to determine a non-responsive target is unhealthy - ```HealthCheckIntervalSeconds: 35```
* The number of healthy/unhealthy checks required to change the health status - ```HealthyThresholdCount: 2``` ```UnhealthyThresholdCount: 5```

**Resources**
* [TargetGroups Documentation](https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/aws-resource-elasticloadbalancingv2-targetgroup.html)
* [Health Checks for Your TargetGroups](https://docs.aws.amazon.com/elasticloadbalancing/latest/application/target-group-health-checks.html)