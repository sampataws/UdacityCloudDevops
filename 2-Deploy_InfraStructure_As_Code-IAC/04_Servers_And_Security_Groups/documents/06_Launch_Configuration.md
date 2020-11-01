The following is the syntax used for ```AutoScaling``` ```LaunchConfiguration```:

```yaml
Type: AWS::AutoScaling::LaunchConfiguration
Properties: 
  AssociatePublicIpAddress: Boolean
  BlockDeviceMappings: 
    - BlockDeviceMapping
  ClassicLinkVPCId: String
  ClassicLinkVPCSecurityGroups: 
    - String
  EbsOptimized: Boolean
  IamInstanceProfile: String
  ImageId: String
  InstanceId: String
  InstanceMonitoring: Boolean
  InstanceType: String
  KernelId: String
  KeyName: String
  LaunchConfigurationName: String
  PlacementTenancy: String
  RamDiskId: String
  SecurityGroups: 
    - String
  SpotPrice: String
  UserData: String
```

The ```ImageId``` and ```Instance``` Type are the only required properties for a ```LaunchConfiguration```. However, there are many useful properties you will likely want to include.

This is an updated WebAppLaunchConfig so that you don’t need external dependencies. Please note this UserData Script is meant to run on Ubuntu Linux.

```yaml
WebAppLaunchConfig:
    Type: AWS::AutoScaling::LaunchConfiguration
    Properties:
      UserData:
        Fn::Base64: !Sub |
         #!/bin/bash
        apt-get update -y
        apt-get install apache2 -y
        systemctl start apache2.service
        cd /var/www/html
        echo "Udacity Demo Web Server Up and Running!" > index.html

      ImageId: ami-005bdb005fb00e791
      IamInstanceProfile: !Ref ProfileWithRolesForOurApp
      SecurityGroups:
      - Ref: WebServerSecGroup
      InstanceType: t3.small
      BlockDeviceMappings:
      - DeviceName: "/dev/sdk"
        Ebs:
          VolumeSize: '10'
```

**In the above example we have done the following:**

* Specified 10gbs for our ```VolumeSize```.
* Referenced the previously defined ```WebServerSecGroup``` for our ```SecurityGroup```
* Set our ```InstanceType``` to ```t3.medium``` for our ```EC2 Instance```
To see all available instance types [click here](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/instance-types.html#AvailableInstanceTypes).

**Resources**
* [Launch Configuration Reference](https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/aws-properties-as-launchconfig.html)