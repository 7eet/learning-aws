## Simple Storage Service
_It is used to store and retreive objects(data) in a bucket._<br>
_It is used for:_
   - Backup and restore
   - Build static website
   - Archive

## Create bucket
```aws s3 mb s3://<bucket-name> --region <region>```
**example**
```aws s3 mb s3://practice --region us-west-2```
> Note: It will use default region when you do not specify the --region parameter

_bucket name is globally unique. Once a bucket is created, the name of that bucket cannot be used by another AWS account in any AWS Region until the bucket is deleted._<br>
[Bucket Guidelines](https://docs.aws.amazon.com/AmazonS3/latest/dev/BucketRestrictions.html)<br>


