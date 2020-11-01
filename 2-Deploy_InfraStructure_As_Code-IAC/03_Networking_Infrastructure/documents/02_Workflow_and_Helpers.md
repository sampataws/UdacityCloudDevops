When creating your ```.yml``` file remember that using the ```Description Field``` is optional. Here we start by adding a short description of our name and project we are working on.

```
Description: >
    Carlos Rivas / Udacity 2019
```


```
The file **AWSWebApp.jpeg** is simply a reference document. 
In other words, since we are creating an infrastructure based on a diagram,
 we exported a version of our diagram from LucidChart in Jpeg format,
 which is supported by our code editor, and we can quickly reference this as a
 visual checklist to make sure we don’t forget one or more components when writing our 
CloudFormation script.
```

##YAML File Available to You as a Resource
The ```network.yml``` file that I use here is included in the **Resources tab** in the left sidebar of this page. The same file is also available in the [Github repository](https://github.com/udacity/nd9991-c2-Infrastructure-as-Code-v1/tree/master/supporting_material).

##Recommended best practices
Although descriptions are optional ,```Resource``` fields are required. Remember to include **at least one resource**(e.g., a VPC, an EC2 instance, a database) in the CloudFormation ```.yml``` script, otherwise it will give an error when you try to run the script..

```
Resources:
    VPC:
        TYPE: AWS::EC2::VPC
```

##Practice Fixing Errors
* Practice fixing errors, as this will help you prepare for real scenarios on the job.
* For instance, try altering correct, working yml scripts to see if they generate an error.
* Practice reading error messages to understand what caused the error, and how to fix them.

##Common commands used
Common commands we’ll use are ```aws cloudformation create-stack```, and ```aws cloudformation update-stack```.