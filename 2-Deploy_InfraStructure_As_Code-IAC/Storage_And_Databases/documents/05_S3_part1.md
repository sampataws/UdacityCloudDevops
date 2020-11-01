##When to use Filestores
* Use filestores instead of databases for large files, such as videos and text documents.
* Configuration files and sensitive encrypted data are best stored in specific filestores rather than inside the servers. Autoscaling groups may create or destroy servers, so keep data that you want to persist in separate resources such as a filestore.

##S3 bucket
* Choose a DNS compliant name for the S3 bucket.

##Command line arguments
```aws s3 ls <link to S3 bucket>```
This line above lists files in the S3 bucket.

```aws s3 cp <file name> <link to S3 bucket> ``` 
This line above copies a file from your local machine to the S3 bucket.

##Versioning
* You can keep past versions of your S3 bucket, which means that deleted files will still exist in prior versions of your S3 bucket.