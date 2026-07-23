<!-- markdownlint-disable MD041 -->
<!-- Match Pinned text fragment prefix- to last word, below. -->
Jump to:
[Pinned&nbsp;repos](https://github.com/sqlxpert#:~:text=policy-,Pinned)
&bull;
<a target="_blank" href="https://github.com/sqlxpert?tab=repositories&q=&type=&language=&sort=stargazers">All&nbsp;repos&nbsp;&nearr;</a>
&bull;
[Contribution&nbsp;graph](https://github.com/sqlxpert#:~:text=contributions,in%20the%20last%20year)
&bull;
[Blog&nbsp;&nearr;](https://sqlxpert.github.io)
<!-- markdownlint-enable MD041 -->

Software engineer focused on cloud infrastructure since&nbsp;2013. Professional relational database experience since&nbsp;1996. Professional programming and Unix/Linux experience since&nbsp;1993. Leadership and business skills from consulting work and an MBA. Training, motivation, team-building, and evaluation skills from past service as a teacher. Past AWS&nbsp;certifications in
[DevOps](https://www.credly.com/badges/e36427dd-92d6-439e-8afd-a66564d1f95d)
and
[databases](https://www.credly.com/badges/bbeb827f-cc55-4977-be15-7691a6879be7).
Current AWS&nbsp;certifications in
[security](https://www.credly.com/badges/c2c1f851-de8c-44df-87b3-58a05260d6fa)&nbsp;(3&times;) and
[networking](https://www.credly.com/badges/5add9caa-9f97-4fef-ba1a-31f59b9014ce). Impeccable writing, technical writing, and presentation skills. 4&nbsp;human languages: English, French, Spanish, and German.

## Technical Skills

I've been writing enterprise-quality open-source AWS utility software since 2017. GitHub provides **proof of work**: revision history plus evidence of real users.

So you can evaluate my technical skills, I've organized short, focused excerpts of my work by topic:

<details>
  <summary>Skills Matrix</summary>

<br/>

Jump to:
[Terraform](#advanced-terraform)
&bull;
[Containers/Docker](#containersdocker)
&bull;
[IAM](#advanced-iam)

### Advanced Terraform

- Secure private network
  - Editable
    [configuration](https://github.com/sqlxpert/docker-python-openapi-kafka-terraform-cloudformation-aws/blob/765999b/terraform/vpc.tf#L177-L206),
    in terms familiar to application developers
  - Automatic, no-edit
    [transformations](https://github.com/sqlxpert/docker-python-openapi-kafka-terraform-cloudformation-aws/blob/765999b/terraform/vpc.tf#L208-L249)
  - Strict, reciprocal security group
    [egress](https://github.com/sqlxpert/docker-python-openapi-kafka-terraform-cloudformation-aws/blob/765999b/terraform/vpc.tf#L321-L333)
    and
    [ingress](https://github.com/sqlxpert/docker-python-openapi-kafka-terraform-cloudformation-aws/blob/765999b/terraform/vpc.tf#L321-L333)
    rules (only known hosts can talk; no private IP address ranges)
  - [Single, shared definition](https://github.com/sqlxpert/docker-python-openapi-kafka-terraform-cloudformation-aws/blob/765999b/terraform/vpc.tf#L294-L314)
    for all VPC private endpoints of both types (avoids repetition and prevents inconsistencies)

### Containers/Docker

- A
  [container definition](https://github.com/sqlxpert/docker-python-openapi-kafka-terraform-cloudformation-aws/blob/main/python_docker/Dockerfile)
  that is
  [secure](https://github.com/sqlxpert/docker-python-openapi-kafka-terraform-cloudformation-aws#innovations-and-best-practices:~:text=Secure%20Docker%20container),
  [small](https://github.com/sqlxpert/docker-python-openapi-kafka-terraform-cloudformation-aws#innovations-and-best-practices:~:text=Small%20Docker%20container%20image),
  but still simple
- Scalable orchestration with
  [Elastic Container Service](https://github.com/sqlxpert/docker-python-openapi-kafka-terraform-cloudformation-aws/blob/main/terraform/ecs.tf)
  (ECS) and
  [load balancing](https://github.com/sqlxpert/docker-python-openapi-kafka-terraform-cloudformation-aws/blob/main/terraform/elb.tf)
  
### Advanced IAM

- Enforce encryption with different KMS keys in different S3 buckets
  - [Central resource control policy](https://github.com/sqlxpert/aws-rcp-s3-require-encryption-kms/blob/3261eb8/terraform/main.tf#L21-L200)
    (RCP) covers buckets in many accounts
  - [Self-service documentation](https://github.com/sqlxpert/aws-rcp-s3-require-encryption-kms/blob/main/README.md#how-to-use)
    reduces developers' dependence on the infrastructure team
  - [Templated test buckets](https://github.com/sqlxpert/aws-rcp-s3-require-encryption-kms/blob/495f7f6/test/test-s3-encryption-tag-rcp.yaml#L101-L234)
    support thorough, realistic, automated tests
  - [Keywords communicate properties](github.com/sqlxpert/aws-rcp-s3-require-encryption-kms/blob/495f7f6/test/tester_rcp.py#L271-L299)
    of test buckets (avoids duplication and prevents inconsistencies)
- Enforce different storage classes in different S3 buckets
  - [Central resource control policy](https://github.com/sqlxpert/aws-rcp-s3-require-intelligent-tiering/blob/8bb0a53/terraform/main.tf#L15-L103)
    (RCP) covers buckets in many accounts
  - Architectural decision record:
    [history](https://github.com/sqlxpert/aws-rcp-s3-require-intelligent-tiering/tree/main#how-it-works)
    of S3, IAM, and AWS Organizations feature releases
  - [Safe permissions delegation trick](https://github.com/sqlxpert/aws-rcp-s3-require-intelligent-tiering/tree/main#:~:text=Detailed%20semantics)
    (&nbsp;`Detailed semantics`&nbsp;, Item&nbsp;4)
- Make least-privilege practical
  - Restrict Lambda function permissions using
    [attribute-based access control](https://github.com/sqlxpert/lights-off-aws/blob/8fb1e8c/cloudformation/lights_off_aws.yaml#L608-L785),
    then protect the ABAC tags with a central
    [service control policy](https://github.com/sqlxpert/lights-off-aws/blob/main/terraform-scp/main.tf)
    (SCP)
  - Balance maintainability with security by
    [restricting instead of rewriting](https://github.com/sqlxpert/docker-python-openapi-kafka-terraform-cloudformation-aws/blob/7fd4bfd/cloudformation/kafka_consumer.yaml#L377-L453)
    an AWS-managed policy
- Avoid infrastructure-as-code duplication with IAM policy variables
  - [Explanation with examples](https://github.com/sqlxpert/step-stay-stopped-aws-rds-aurora/issues/10#issuecomment-3919113672),
    in a response to a user
  - [CloudFormation parameter](https://github.com/sqlxpert/step-stay-stopped-aws-rds-aurora/blob/d6d3838/cloudformation/step_stay_stopped_aws_rds_aurora.yaml#L136-L144)
  - [Insertion into IAM policy](https://github.com/sqlxpert/step-stay-stopped-aws-rds-aurora/blob/d6d3838/cloudformation/step_stay_stopped_aws_rds_aurora.yaml#L672)
</details>

<!-- If last word changes, update Pinned text fragment prefix- above. -->
