# Using Python/Boto3 in AWSCLI

- Script for creating bucket and file 

```import logging
import boto3
from botocore.exceptions import ClientError


def create_bucket(bucket_name, region=None):
    """Create an S3 bucket in a specified region

    If a region is not specified, the bucket is created in the S3 default
    region (us-east-1).

    :param bucket_name: Bucket to create
    :param region: String region to create bucket in, e.g., 'us-west-2'
    :return: True if bucket created, else False
    """

    # Create bucket
    try:
        if region is None:
            s3_client = boto3.client('s3')
            s3_client.create_bucket(Bucket=bucket_name)
        else:
            s3_client = boto3.client('s3', region_name=region)
            location = {'LocationConstraint': region}
            s3_client.create_bucket(Bucket=bucket_name,
                                    CreateBucketConfiguration=location)
    except ClientError as e:
        logging.error(e)
        return False
    return True

def upload_file(file_name, bucket, object_name=None):
    """Upload a file to an S3 bucket

    :param file_name: File to upload
    :param bucket: Bucket to upload to
    :param object_name: S3 object name. If not specified then file_name is used
    :return: True if file was uploaded, else False
    """

    # If S3 object_name was not specified, use file_name
    if object_name is None:
        object_name = os.path.basename(file_name)

    # Upload the file
    s3_client = boto3.client('s3')
    try:
        response = s3_client.upload_file(file_name, bucket, object_name)
    except ClientError as e:
        logging.error(e)
        return False
    return True

REGION="eu-west-1"
BUCKET_NAME="eng122-pravin-bucket-task"
OBJECT_NAME="object.txt"
FILE_NAME="test.txt"
create_bucket(BUCKET_NAME,REGION)

upload_file(
    FILE_NAME, BUCKET_NAME, OBJECT_NAME
)
```

- Script for downloading/retrieving file from bucket 

```
import boto3

s3 = boto3.client('s3')
s3.download_file('eng122-pravin-bucket-task', 'object.txt', 'test.txt')
```

- Script for deleting item from bucket

``` 
import boto3

s3 = boto3.resource('s3')
s3.Object('eng122-pravin-bucket-task', 'object.txt').delete()

```

- Script for deleting bucket itself

```
import boto3

AWS_REGION = "eu-west-1"

resource = boto3.resource("s3", region_name=AWS_REGION)

bucket_name = "eng122-pravin-bucket-task"

s3_bucket = resource.Bucket(bucket_name)
s3_bucket.delete()
```

- Remember to use `python` followed by the `.py` file to run it


