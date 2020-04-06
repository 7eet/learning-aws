## Simple Storage Service
_It is used to store and retreive objects(data)._<br>
_Objects are store in a bucket._<br>
_Create a bucket then store objects in it. You can do this with AWS Console, CLI and SKDs._<br>
_[more](https://aws.amazon.com/s3/)_
_It is used for:_
   - Backup and restore
   - Build static website
   - Archive

## Create bucket
```
  aws s3 mb s3://<bucket-name> --region <region>
```
  **or**
```
  aws s3api create-bucket --bucket my-bucket --region us-east-1
```
_with this you can optionally specify the accounts or groups that should be granted specific permissions on the bucket._<br>
[create-bucket](https://docs.aws.amazon.com/cli/latest/reference/s3api/create-bucket.html)

__example__

```aws s3 mb s3://practice --region us-west-2```

> Note: It will use default region when you do not specify the --region parameter. The bucket name is globally unique. Once a bucket is created, the name of that bucket cannot be used by another AWS account in any AWS Region until the bucket is deleted.<br>
[Bucket Guidelines](https://docs.aws.amazon.com/AmazonS3/latest/dev/BucketRestrictions.html)<br>

## Upload objects to bucket

### cp command

#### upload file to bucket
  ```
    aws s3 cp file.txt s3://bucket-name
  ```

#### copy a object from one bucket to another bucket
  ```
    aws s3 cp s3://bucket-one/file.txt s3://another-bucket
  ```

#### upload a folder to bucket
  ```
    aws s3 cp /dir/ s3://bucket-name/folder-name/ --recursive
  ```

### mv command

#### move local file to bucket
  ``` 
    aws s3 mv file.txt s3://bucket-name
  ```

#### move object from bucket to local system
  ```
    aws s3 mv s3://bucket-name/file.txt . 
  ```

## sync command

### sync bucket with local directory
  ```
    aws s3 sync . s3://bucket-name
  ```
  _It will add all the new files and modified files to a bucket._

### sync local directory
  ```
    aws s3 sync s3://bucket-name/dir .
  ```
  _It download all the files which are not present in this directory and modified in bucket but not in this directory._


## Download object

### cp command

#### download a file from bucket
  ```
    aws s3 cp s3://bucket-name/file.txt .
  ```
#### download a whole bucket
  ```
    aws s3 cp s3://bucket-name /path/to/dir --recursive
  ```

## List objects
### does not traverse inside the folder
  ```
    aws s3 ls s3://bucket-name
  ```
### traverse inside folder
  ```
    aws s3 ls s3://bucket-name --recursive
  ```
### readable format
  ```
    aws s3 ls s3://bucket-name --human-readable --summarize
  ```

## Delete object
_to delete a single object._<br>
```
  aws s3 rm s3://bucket-name/file.txt

  aws s3api delete-object --bucket bucket-name --key file.txt
```

_to delete all objects in a bucket._<br>
```
  aws s3 rm s3://bucket-name --recursive
```

## Delete bucket
### delete empty bucket
  ```
    aws s3 rb s3://bucket-name
    
    aws s3api delete-bucket --bucket bucket-name
    
  ```
### delete non-empty bucket
  ```
    aws s3 rb s3://bucket-name --recursive --force
  ```

# s3api 
  
## delete server-side encryption
```
  aws s3api delete-bucket-encryption --bucket bucket-name
```

## delete bucket policy
```
  aws s3api delete-bucket-policy --bucket my-bucket
```

## delete website configuration from bucket
```
  aws s3api delete-bucket-website --bucket my-website
```

## delete object tagging
```
  aws s3api delete-object-tagging --bucket bucket-name --key file.txt
```

## get Access Control List (ACL)
```
  aws s3api get-bucket-acl --bucket my-bucket
```

## retrieve the server-side configuration for the bucket
```
  aws s3api get-bucket-encryption --bucket my-bucket
```

## retrieve the location of bucket
```
  aws s3api get-bucket-location --bucket my-bucket
```

## retrieve the logging status for a bucket
```
  aws s3api get-bucket-logging --bucket my-bucket
```

## retrieve the bucket policy
```
  aws s3api get-bucket-policy --bucket my-bucket
```

## retrieve the policy status for a bucket indicating whether the bucket is public
```
  aws s3api get-bucket-policy-status --bucket my-bucket
```

## retrieve the versioning configuration
```
  aws s3api get-bucket-versioning --bucket my-bucket
```

## retrieve the static website configuration
```
  aws s3api get-bucket-website --bucket my-website
```

## retrieve the ACL of object
```
  aws s3api get-object-acl --bucket my-bucket --key file.txt
```

## retrieve object tagging
```
  aws s3api get-object-tagging --bucket my-bucket --key file.txt
```

## verifies access to bucket
```
  aws s3api head-bucket --bucket my-bucket
```

## retrieve the metadata of a object
```
  aws s3api head-object --bucket my-bucket --key file.txt
```

## list buckets
```
  aws s3api list-buckets
```

## list objects
```
  aws s3api list-objects --bucket my-bucket
```

## put bucket ACL
[read](https://docs.aws.amazon.com/cli/latest/reference/s3api/put-bucket-acl.html)

## put bucket policy
[read](https://docs.aws.amazon.com/cli/latest/reference/s3api/put-bucket-policy.html)

## put bucket website
[read](https://docs.aws.amazon.com/cli/latest/reference/s3api/put-bucket-website.html)



