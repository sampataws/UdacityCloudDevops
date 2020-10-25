#How to run CloudFormation
* For this example, we’ll assume your CloudFormation file name is called ```testcfn.yml```, and you’re giving your stack the name ```myfirsttest```.
* **In the terminal**, to use your yml code to request the resources, type the following in the same directory as your yml file:

```
aws cloudformation create-stack 
--stack-name myfirsttest 
--region us-west-2 
--template-body file://testcfn.yml
```
* Alternatively, you can write a **shell script** (.sh) file as:

```
aws cloudformation create-stack 
--stack-name $1 
--template-body file://$2  
--parameters file://$3 
--capabilities "CAPABILITY_IAM" "CAPABILITY_NAMED_IAM" 
--region=us-west-2
```
were ```$1```, ```$2```, and ```$3``` can be replaced with the actual values. Note the ```--parameters``` and ```--capabilities``` options that we will learn in the upcoming lesson.
* You can also try a **batch script** (.bat) with a similar syntax, except that the actual values can be written as ```%1``` instead as ```$1```.
* You may also want to use **update-stack** when you want to update an existing stack instead of destroying your stack and creating a new one. The syntax is similar to before:
```
aws cloudformation update-stack 
--stack-name $1 
--template-body file://$2  
--parameters file://$3 
--capabilities "CAPABILITY_IAM" "CAPABILITY_NAMED_IAM" 
--region=us-west-2
```