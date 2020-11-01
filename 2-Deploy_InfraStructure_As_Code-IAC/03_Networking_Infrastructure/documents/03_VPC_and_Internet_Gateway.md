CloudFormation Scripts and Parameter files
Our Preferred way of writing CloudFormation Scripts is in YAML Format, like this:
```yaml
Parameters:
    #Parameters are entirely optional.**
    #but using them will make your cloudformation templates more reusable**

Resources:
  ResourceName:
    ResourceType
    Properties: 
```
Let’s discuss the Parameters and Resources.

**A. Parameters section of our CloudFormation script**

Any named parameters in the Parameters section of our CloudFormation script will need to have a matching value in a separate, Parameter file, which is in JSON format. A sample JSON-formatted Parameter file is:
```json
[
    {
        "ParameterKey": "EnvironmentName",
        "ParameterValue": "UdacityProject"
    }
]
```

Having this additional file with actual parameter values, allows you to change data that is used by your CloudFormation script without the risk of having to modify the script directly and possibly introduce a typo or some sort of logical error.

**B. Resources section of our CloudFormation script**

This is actually the only mandatory section of our script because this is where we actually build resources, such as Servers, Gateways, VPN Connections and more.

Each resource you add to this section will have the same sections as in our example below.

* A Name which can be anything that makes sense to you
* A Type which tells CloudFormation which kind of resource it is
* Some additional properties that are specific to the resource, which you can find in the CloudFormation documentation.
```yaml
My_IAM_Roles_for_my_EC2_Web_Server:
    Type: AWS::IAM::InstanceProfile
    Properties: 
      Roles:
        - UdacityS3ReadOnlyEC2
```
**Connecting VPC's & Internet Gateways**
It's important to note when connecting an ```Internet Gateway``` to a ```VPC```, we need to define an additional resource called ```InternetGatewayAttachment```. This attachment references both the VPC and the InternetGateway. Here is the syntax for the following connection:

```yaml
Type: AWS::EC2::VPCGatewayAttachment
Properties: 
  InternetGatewayId: String
  VpcId: String
  VpnGatewayId: String
```

**Don't hard-code parameters**
Avoid hard coding parameter values. Instead, use a separate parameter file to store parameter values. Note that the parameter file should be in ```.json``` format, as ```.yml``` format is not yet supported for the parameter file.

Here is an example parameters file from ```network-parameters.json``` which is holding key-value pairs for the ```Environment``` & ```VpcCiIDR```.

```json
[
    {
        "ParameterKey": "EnvironmentName",
        "ParameterValue": "UdacityProject"
    },
    {
        "ParameterKey": "VpcCIDR",
        "ParameterValue": "10.0.0.0/16"
    }
]
```

**Setting Parameters**

```Parameters``` should be declared above your ```Resources```:

```text
Parameters:
# whatever you consider a changing value, put it as a parameter instead of hard-coding it into your script
Resources:
```

and should follow the general format of:

```yaml
Parameters:
  ParameterLogicalID:
    Type: DataType
    ParameterProperty: value
```

Here we set the ```EnvironmentName``` parameter in our sample code from the video:

```yaml
Parameters:
    EnvironmentName:
        Description: An Environment name that will be prefixed to resources
        Type: String
```

**Default Parameters**

You can also provide default values for parameters in case one was not passed in. In this example you can see that ```VpcCIDR``` has a default value of ```10.0.0.0/16```.

```yaml
Parameters:
    EnvironmentName:
        Description: An Environment name that will be prefixed to resources
        Type: String

    VpcCIDR:
        Description: Please enter the IP range (CIDR notation) for this
        Type: String
        Default: 10.0.0.0/16
```


**Calling CloudFormation**

When calling AWS CloudFormation, you’ll pass in the name of the ```.yml``` file as well as the name of the parameter file as parameters to the CloudFormation call.

For example:
```text
aws cloudformation create-stack --stack-name MyStack --template-body file://MyCloudformationScript.yml  --parameters file://MyEnvironmentVariables.json 
```
* Note that CloudFormation knows to create the resources in order, based on their dependencies (VPC and InternetGateway, before creating the InternetGatewayAttachment).

**Further Resources**

* The ```network.yml``` file that I use in this lesson is included in the Resources tab in the left sidebar of this page, if you'd like to download it.
* [Parameters](https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/parameters-section-structure.html)
* [VPC](https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/aws-resource-ec2-vpc.html)
* [VPCCidrBlock](https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/aws-resource-ec2-vpccidrblock.html)
* [Internet Gateway](https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/aws-resource-ec2-internetgateway.html)