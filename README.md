# Why?
This repository serves as a step-by-step guide to create a simple aws application using
- Github Actions (cicd)
  - Used for small, frequent commits
- AWS Cloudformation template
- AWS Orgformation template
  - Hosting a simple EC2 Instance

# Configure AWS Credentials for Github Actions (OpenID Connect - OIDC)
1. Add an Identity provider through the AWS console.</br>
`IAM > Identity providers > Add provider > {Add Provider URL & Audience} Add Provider`

2. Create an IAM role and select Identity provider created above.</br>
   `IAM > Roles > Create role > Web Identity > {Select Identity provider token & audience} Next > {Add permissions} Next > {Add Role name} Create role`

- Helpful resources:
  - [Configuring AWS Credentials for Github Actions](https://github.com/aws-actions/configure-aws-credentials)
  - [Create IAM Role in AWS Console](https://www.automat-it.com/post/using-github-actions-with-aws-iam-roles)
    - Security best practices in IAM: applications and services should use IAM roles instead or IAM users.
    - This is why we setup Github Actions using OIDC.
  - [Deploying with sam](https://docs.aws.amazon.com/serverless-application-model/latest/developerguide/serverless-sam-cli-command-reference.html)

3. Further Configurations
   1. If it complains about Cloudformation ChangeSet is not allowed, create / attach a policy with to Role Permissions.

