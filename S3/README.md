## Simple Storage Service
_It is used to store and retreive objects(data)._<br>
_Objects are store in a bucket._<br>
_Create a bucket then store objects in it. You can do this with AWS Console, CLI and SKDs._<br>
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

## Upload objects to bucket

### cp command
 - _upload file to bucket_
  ```
    aws s3 cp file.txt s3://bucket-name
  ```
 - _copy a object from one bucket to another bucket_
  ```
    aws s3 cp s3://bucket-one/file.txt s3://another-bucket
  ```

### mv command


## Download object
### cp command
 - _download a file from bucket_
  ```
    aws s3 cp s3://bucket-name/file.txt .
  ```

## Delete object
```
  aws s3api delete-object --bucket bucket-name --key file.txt
```
