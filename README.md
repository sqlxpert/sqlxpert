<!-- markdownlint-disable MD041 -->
<!-- Match Pinned text fragment prefix- to last displayed word, below. -->
Jump to:
[Pinned&nbsp;repos](https://github.com/sqlxpert#:~:text=orchestration.-,Pinned)
&bull;
[Contribution&nbsp;graph](https://github.com/sqlxpert#:~:text=contributions,-in%20the%20last%20year)
&bull;
[All&nbsp;repos&nbsp;&nearr;](https://github.com/sqlxpert?tab=repositories&q=&type=&language=&sort=stargazers)
&bull;
[LinkedIn&nbsp;&nearr;](https://www.linkedin.com/in/marcelin)
&bull;
[Blog&nbsp;&nearr;](https://sqlxpert.github.io)
<!-- markdownlint-enable MD041 -->

## Competencies

<details name="competencies">
  <summary>Terraform</summary>

<br/>

- Secure private network:
  - An editable
    [configuration map](https://github.com/sqlxpert/docker-python-openapi-kafka-terraform-cloudformation-aws/blob/765999b/terraform/vpc.tf#L177-L206)
    feeds `for_each`
    [sets and maps](https://github.com/sqlxpert/docker-python-openapi-kafka-terraform-cloudformation-aws/blob/765999b/terraform/vpc.tf#L208-L249)
  - Strict reciprocal security group
    [egress](https://github.com/sqlxpert/docker-python-openapi-kafka-terraform-cloudformation-aws/blob/765999b/terraform/vpc.tf#L321-L333)
    and
    [ingress](https://github.com/sqlxpert/docker-python-openapi-kafka-terraform-cloudformation-aws/blob/765999b/terraform/vpc.tf#L321-L333)
    rules permit traffic between identified hosts only.
- A
  [data-driven](https://github.com/sqlxpert/lights-off-aws/blob/dfe86f7/terraform-multi/variables.tf#L16-L24),
  not hard-coded,
  [validation rule and error message](https://github.com/sqlxpert/lights-off-aws/blob/dfe86f7/terraform-multi/variables.tf#L33-L40)
- [Intuitive defaults](https://github.com/sqlxpert/lights-off-aws/blob/dfe86f7/terraform-multi/variables.tf#L168-L169)
  with
  [minimal code](https://github.com/sqlxpert/lights-off-aws/blob/dfe86f7/terraform-multi/locals.tf#L50-L57),
  for an
  [AWS API data type](https://docs.aws.amazon.com/AWSCloudFormation/latest/APIReference/API_StackSetOperationPreferences.html#:~:text=either%20MaxConcurrentCount,not%20both)
  that can't be reduced to a Terraform HCL type specification
- A new
  [S3 object version triggers a Terraform change](https://github.com/sqlxpert/lights-off-aws/blob/c86306c/terraform/main.tf#L213).
  Most users
  [forget `versionID`](https://github.com/cloudposse/terraform-aws-cloudformation-stack/blob/ce3265a/README.md?plain=1#L68)&nbsp;.

</details>

<details name="competencies">
  <summary>CloudFormation</summary>

<br/>

- The same template makes a single-account, single-region stack or a centrally-managed, multi-account, multi-region Stack**Set**:
  - "Partial ARN"
    [parameter formats](https://github.com/sqlxpert/lights-off-aws/blob/8fb1e8c/cloudformation/lights_off_aws.yaml#L302-L315)
    are
    [not specific to any region](https://github.com/sqlxpert/lights-off-aws/blob/8fb1e8c/cloudformation/lights_off_aws.yaml#L1000-L1003).
  - 1&nbsp;template with
    [conditions](https://github.com/sqlxpert/backup-events-aws/blob/fa043c0/cloudformation/backup_events_aws.yaml#L376-L378)
    replaces
    [3&nbsp;separate&nbsp;templates](https://github.com/aws-samples/aws-blog-automate-amazon-rds-cross-account-backups).
- [Validation rules](https://github.com/sqlxpert/10-minute-aws-client-vpn/blob/f63ded4/cloudformation/10-minute-aws-client-vpn.yaml#L334-L387)
  and a
  [condition](https://github.com/sqlxpert/10-minute-aws-client-vpn/blob/f63ded4/cloudformation/10-minute-aws-client-vpn.yaml#L396-L398)
  accommodate different kinds of inputs and different cardinalities.
- A least-privilege
  [CloudFormation service role](https://github.com/sqlxpert/step-stay-stopped-aws-rds-aurora/blob/main/cloudformation/step_stay_stopped_aws_rds_aurora_prereq.yaml)
  protects each stack and "confused deputy" risk.
- [Placeholder parameters](https://github.com/sqlxpert/step-stay-stopped-aws-rds-aurora/blob/d6d3838/cloudformation/step_stay_stopped_aws_rds_aurora.yaml#L10-L20)
  help AWS&nbsp;Console users to name stacks and find documentation.

</details>

<details name="competencies">
  <summary>IAM</summary>

<br/>

- Enforce KMS encryption in S3:
  - One central
    [resource control policy](https://github.com/sqlxpert/aws-rcp-s3-require-encryption-kms/blob/3261eb8/terraform/main.tf#L21-L200)
    (RCP) covers buckets in many accounts.
  - [Tags and self-service documentation](https://github.com/sqlxpert/aws-rcp-s3-require-encryption-kms/blob/main/README.md#how-to-use)
    reduce developers' dependence on the infrastructure team
  - [Templated test buckets](https://github.com/sqlxpert/aws-rcp-s3-require-encryption-kms/blob/495f7f6/test/test-s3-encryption-tag-rcp.yaml#L101-L234)
    support thorough, realistic, automated tests
  - [Keywords communicate properties](github.com/sqlxpert/aws-rcp-s3-require-encryption-kms/blob/495f7f6/test/tester_rcp.py#L271-L299)
    of test buckets without duplicate code
- Enforce S3 storage class:
  - One central
    [resource control policy](https://github.com/sqlxpert/aws-rcp-s3-require-intelligent-tiering/blob/8bb0a53/terraform/main.tf#L15-L103)
    (RCP) covers buckets in many accounts.
  - [History](https://github.com/sqlxpert/aws-rcp-s3-require-intelligent-tiering/tree/main#how-it-works)
    of S3, IAM, and AWS Organizations feature releases provides an architectural decision record.
  - [Safe permissions delegation trick](https://github.com/sqlxpert/aws-rcp-s3-require-intelligent-tiering/tree/main#:~:text=Detailed%20semantics)
    (&nbsp;`Detailed semantics`&nbsp;, Item&nbsp;4)
- Restrict Lambda function permissions using
  [attribute-based access control](https://github.com/sqlxpert/lights-off-aws/blob/8fb1e8c/cloudformation/lights_off_aws.yaml#L608-L785),
  then protect ABAC tags with a
  [service control policy](https://github.com/sqlxpert/lights-off-aws/blob/main/terraform-scp/main.tf)
  (SCP)
- [Restrict instead of rewriting](https://github.com/sqlxpert/docker-python-openapi-kafka-terraform-cloudformation-aws/blob/7fd4bfd/cloudformation/kafka_consumer.yaml#L377-L453)
  an AWS-managed policy, for self-documenting, maintainable least-privilege
- IAM policy variables avoid code duplication:
  - [Explanation with examples](https://github.com/sqlxpert/step-stay-stopped-aws-rds-aurora/issues/10#issuecomment-3919113672)
  - [CloudFormation parameter](https://github.com/sqlxpert/step-stay-stopped-aws-rds-aurora/blob/d6d3838/cloudformation/step_stay_stopped_aws_rds_aurora.yaml#L136-L144)
  - [Insertion into IAM policy](https://github.com/sqlxpert/step-stay-stopped-aws-rds-aurora/blob/d6d3838/cloudformation/step_stay_stopped_aws_rds_aurora.yaml#L672)

</details>

<details name="competencies">
  <summary>Python</summary>

<br/>

- Object-oriented design:
  - [Harmonizes AWS API inconsistencies](https://github.com/sqlxpert/lights-off-aws/blob/c86306c/python/lights_off_aws.py#L235-L461)
    &mdash; method names; input argument names, types (ID versus ARN), and cardinality; and output object keys
  - [Accommodates varied AWS resource types](https://github.com/sqlxpert/lights-off-aws/blob/c86306c/python/lights_off_aws.py#L464-L601)
  - [Describes capabilities](https://github.com/sqlxpert/lights-off-aws/blob/c86306c/python/lights_off_aws.py#L607-L673)
    at a glance and supports
    [extensibility](https://github.com/sqlxpert/lights-off-aws/tree/main#extensibility:~:text=Extensibility%20details...)
- OpenAPI provides a clear
  [API&nbsp;specification](https://github.com/sqlxpert/docker-python-openapi-kafka-terraform-cloudformation-aws/blob/main/python_docker/hello_api.openapi.yaml)
  and automatic input validation with
  [minimal, focused code](https://github.com/sqlxpert/docker-python-openapi-kafka-terraform-cloudformation-aws/blob/1edaa6a/python_docker/hello_api.py#L160-L247).
- Clear and consistent
  [error-handling functions](https://github.com/sqlxpert/stay-stopped-aws-rds-aurora/blob/08bd58c/stay_stopped_aws_rds_aurora.py#L94-L264)
- [Structured JSON logs](https://github.com/sqlxpert/lights-off-aws/blob/c86306c/python/lights_off_aws.py#L63-L98),
  searchable by humans and readable by machines
- [Self-documenting regular expression](https://github.com/sqlxpert/lights-off-aws/blob/c86306c/python/lights_off_aws.py#L26-L45)

</details>

<details name="competencies">
  <summary>Containers/Docker</summary>

<br/>

- A simple
  [container definition](https://github.com/sqlxpert/docker-python-openapi-kafka-terraform-cloudformation-aws/blob/main/python_docker/Dockerfile)
  yields a
  [secure](https://github.com/sqlxpert/docker-python-openapi-kafka-terraform-cloudformation-aws#innovations-and-best-practices:~:text=Secure%20Docker%20container)
  and
  [small](https://github.com/sqlxpert/docker-python-openapi-kafka-terraform-cloudformation-aws#innovations-and-best-practices:~:text=Small%20Docker%20container%20image)
  image.
- [Elastic Container Service](https://github.com/sqlxpert/docker-python-openapi-kafka-terraform-cloudformation-aws/blob/main/terraform/ecs.tf)
  (ECS) and
  [load balancing](https://github.com/sqlxpert/docker-python-openapi-kafka-terraform-cloudformation-aws/blob/main/terraform/elb.tf)
  support scalable orchestration.

</details>

<details name="competencies">
  <summary>Reliability</summary>

<br/>

- Diagnosing and
  [fixing race conditions](https://github.com/sqlxpert/stay-stopped-aws-rds-aurora#perspective:~:text=idempotence%2C%20race%20conditions,latent%20bugs...)
  (timing bugs)
- ["5&nbsp;AWS&nbsp;Services, 5&nbsp;Different&nbsp;Approaches to Idempotence"](https://builder.aws.com/content/2xTBvqInpTdbmC91IDT1hFeZQMQ/5-aws-services-5-different-approaches-to-idempotence)
- [Rejecting the legacy AWS SDK retry mode](https://github.com/sqlxpert/lights-off-aws/blob/c86306c/python/lights_off_aws.py#L225),
  years
  [in&nbsp;advance](https://aws.amazon.com/blogs/developer/announcing-updated-retry-behavior-for-aws-sdks-and-tools/#:~:text=currently%20default%20to,mode)
- [AWS SDK pagination](https://github.com/sqlxpert/lights-off-aws/blob/c86306c/python/lights_off_aws.py#L303-L305)
- [Queues, retries, and timeouts](https://github.com/sqlxpert/lights-off-aws/blob/main/media/lights-off-aws-architecture-and-flow.png)

</details>

<!-- If last displayed word changes, update Pinned text fragment prefix- above. -->
