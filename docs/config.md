# Configuration

tfaction.yaml

```yaml
---
targets:
- working_directory: aws/
  target: aws/
  aws_region: ap-northeast-1
  s3_bucket_name_plan_file: '<S3 Bucket Name for Terraform Plan File>'
  s3_bucket_name_tfmigrate_history: '<S3 Bucket Name for tfmigrate history files>'
  template_dir: templates/aws
  assume_role_arns:
    tfmigrate_plan: arn:aws:iam::000000000000:role/GitHubActionsTerraformPR
    terraform_plan: arn:aws:iam::000000000000:role/GitHubActionsTerraformPR
    tfmigrate_apply: arn:aws:iam::000000000000:role/GitHubActionsTerraformMain
    terraform_apply: arn:aws:iam::000000000000:role/GitHubActionsTerraformMain

- working_directory: github/services/
  target: github/
  aws_region: ap-northeast-1
  s3_bucket_name_plan_file: '<S3 Bucket Name for Terraform Plan File>'
  s3_bucket_name_tfmigrate_history: '<S3 Bucket Name for tfmigrate history files>'
  template_dir: templates/github
  assume_role_arns:
    tfmigrate_plan: arn:aws:iam::000000000000:role/GitHubActionsTerraformPRGitHub
    terraform_plan: arn:aws:iam::000000000000:role/GitHubActionsTerraformPRGitHub
    tfmigrate_apply: arn:aws:iam::000000000000:role/GitHubActionsTerraformMainGitHub
    terraform_apply: arn:aws:iam::000000000000:role/GitHubActionsTerraformMainGitHub

label_prefixes:
  target: "target:"
  tfmigrate: "migrate:"
  ignore: "ignore:"
```