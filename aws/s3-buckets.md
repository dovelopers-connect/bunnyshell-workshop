# S3 Buckets

Create bucket

{% embed url="https://docs.aws.amazon.com/cli/latest/reference/s3api/create-bucket.html" %}
AWS reference
{% endembed %}

```bash
aws s3api create-bucket --bucket muses --region eu-central-1 --create-bucket-configuration LocationConstraint=eu-central-1
```

List all buckets

`aws s3 ls`

List files in a bucket

`aws s3 ls s3://muses`
