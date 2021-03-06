#S3 & CloudFront
In this hands-on exercise, you will create a S3 bucket with a Cloud Front distribution to speed up our the delivery of content to our website.

##Prerequisites:
* AWS Account
##Topics Covered:
By the end of this lab, you will be able to:

* Create and configure a bucket
* Upload an object to a bucket
* Create distribution

##Steps:
1. ###Create S3 Bucket
    * On the AWS Management Console page, type ```S3``` in the ```Find Services``` box and then select ```S3```.
    * Click ```Create bucket```
    * Enter a ```Bucket name```.
        * **Note**: Bucket names must be globally unique.
    * Click the ```Create``` button.
    * Once the bucket is created, click on the name of the bucket to open the bucket to the contents.
2. ###Upload Object to Bucket
    * Once the bucket is open to its contents, click the ```Upload``` button.
    * Click the ```Add Files``` button.
    * Select a file from your local computer to upload.
    * Click ```Open```.
    * Click ```Upload```.
3. ###Create CloudFront Distribution
    * Select ```Services``` from the top left corner.
    * Enter ```cloud front``` in the ```Find a service by name or feature``` text box and select ```Cloud Front```.
    * Click ```Create Distribution```.
    * Under the ```Web``` delivery method, select ```Get Started```.
    * Under ```Origin Settings```:
    * Under ```Origin Domain Name```, select the S3 bucket that you just created.
    * Under ```Origin Path```, enter ```/``` to indicate the root level.
    * Leave the defaults for the rest of the options.
    * Click ```Create Distribution```.
        * ```Note```: It may take up to 10 minutes for the CloudFront Distribution to be created.
4. ###Delete Bucket and Distribution
    * To delete the Cloud Front distribution, click on the radio button next to the ```Delivery Method``` for the distribution. Click ```Disable``` and then ```Yes, Disable```. Click ```Close```.
    * Once the distribution is disabled, you can delete it by selecting the radio button next to the ```Delivery Method``` and clicking the ```Delete``` button.
    * To delete the S3 bucket, navigate to S3, but clicking on ```Services``` and typing ```S3``` in the ```Find Services``` box and then select ```S3```.
    * Select the radio button next to the name of the bucket you want to delete.
    * Click ```Delete```.
    * Type the name of the bucket to confirm deletion.
    * Click the ```Confirm``` button.
