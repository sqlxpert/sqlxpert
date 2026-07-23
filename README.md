<!-- markdownlint-disable MD041 -->
Jump to:
[**Pinned&nbsp;repos**](https://github.com/sqlxpert#:~:text=graph-,Pinned)
&bull;
[**All&nbsp;repos**](https://github.com/sqlxpert?tab=repositories&q=&type=&language=&sort=stargazers)&nbsp;&nearr;
&bull;
[**Contribution&nbsp;graph**](https://github.com/sqlxpert#:~:text=contributions,in%20the%20last%20year)
<!-- markdownlint-enable MD041 -->

# Skills Matrix

## Advanced Terraform

- Secure private network
  - Editable application
    [configuration](https://github.com/sqlxpert/docker-python-openapi-kafka-terraform-cloudformation-aws/blob/765999b/terraform/vpc.tf#L177-L206)
  - Automatic, no-edit
    [transformations](https://github.com/sqlxpert/docker-python-openapi-kafka-terraform-cloudformation-aws/blob/765999b/terraform/vpc.tf#L208-L249)
  - Strict, reciprocal security group
    [egress](https://github.com/sqlxpert/docker-python-openapi-kafka-terraform-cloudformation-aws/blob/765999b/terraform/vpc.tf#L321-L333)
    and
    [ingress](https://github.com/sqlxpert/docker-python-openapi-kafka-terraform-cloudformation-aws/blob/765999b/terraform/vpc.tf#L321-L333)
    rules (only known hosts can talk; no private IP address ranges)

## Containers/Docker

- [Secure](https://github.com/sqlxpert/docker-python-openapi-kafka-terraform-cloudformation-aws#innovations-and-best-practices:~:text=Secure%20Docker%20container),
  [small](https://github.com/sqlxpert/docker-python-openapi-kafka-terraform-cloudformation-aws#innovations-and-best-practices:~:text=Small%20Docker%20container%20image),
  but still simple
  [container definition](https://github.com/sqlxpert/docker-python-openapi-kafka-terraform-cloudformation-aws/blob/b409cdb/python_docker/Dockerfile)

## Identity and Access Management policy language

- Require encryption with KMS keys specified in S3 bucket tags
  - [Central resource control policy](https://github.com/sqlxpert/aws-rcp-s3-require-encryption-kms/blob/3261eb8/terraform/main.tf#L21-L200)
    covers buckets in many accounts
  - [Self-service documentation](github.com/sqlxpert/aws-rcp-s3-require-encryption-kms/blob/main/README.md#how-to-use)
    helps developers
  - [Templated test buckets](https://github.com/sqlxpert/aws-rcp-s3-require-encryption-kms/blob/495f7f6/test/test-s3-encryption-tag-rcp.yaml#L101-L234)
    support thorough, realistic, automated tests
  - [Keywords communicate properties](github.com/sqlxpert/aws-rcp-s3-require-encryption-kms/blob/495f7f6/test/tester_rcp.py#L271-L299)
    of test buckets (avoids duplication, inconsistencies)
- Require a storage class specified in an S3 bucket tag
  - Architectural decision record:
    [history](https://github.com/sqlxpert/aws-rcp-s3-require-intelligent-tiering/tree/main#how-it-works)
    of S3, IAM, and AWS Organizations feature releases
  - [Safe permissions delegation trick](https://github.com/sqlxpert/aws-rcp-s3-require-intelligent-tiering/tree/main#:~:text=Detailed%20semantics)
    ("Detailed semantics", Item&nbsp;4)

[More examples coming...]
