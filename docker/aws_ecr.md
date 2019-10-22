# AWS ECR

1.- First Configure aws-cli
2.- in ~/.aws/credential

```
[default]
aws_access_key_id = XXXXXXXX
aws_secret_access_key = XXXXXXX

```

3.- in ~/.aws/config set up the region you want to use

```
[default]
region = eu-central-1
output = json

[profile clarity-dev]
region=eu-central-1
source_profile = default
output=json

```


