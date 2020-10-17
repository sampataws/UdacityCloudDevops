#Cloud Front
CloudFront is used as a global content delivery network (CDN). Cloud Front speeds up the delivery of your content through Amazon's worldwide network of mini-data centers called Edge Locations.

CloudFront works with other AWS services, as shown below, as an origin source for your application:

* Amazon S3
* Elastic Load Balancing
* Amazon EC2
* Lambda@Edge
* AWS Shield

##Tips
* CloudFront is found under the Networking & Content Delivery section on the AWS Management Console.
* Amazon countinously adds new Edge Locations.
* CloudFront ensures that end-user requests are served from the closest edge location.
* CloudFront works with non-AWS origin sources.
* You can use GeoIP blocking to serve content (or not serve content) to specific countries.
* Cache control headers determine how frequently CloudFront needs to check the origin for an updated version your file.
* The maximum size of a single file that can be delivered through Amazon CloudFront is 20 GB.

**Resources**
* [Amazon CloudFront Overview](https://aws.amazon.com/cloudfront/)
* [What is Amazon CloudFront](https://docs.aws.amazon.com/AmazonCloudFront/latest/DeveloperGuide/Introduction.html)