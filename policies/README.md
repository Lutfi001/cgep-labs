# Policy as Code Library (NIST 800-53)

This directory contains Rego policies evaluated via Conftest against Terraform plans. Each policy enforces a specific NIST 800-53 control for a target cloud provider.

## Policy Inventory

| Control ID | Cloud | Policy File | Package Namespace | Description |
| :--- | :--- | :--- | :--- | :--- |
| **SC-28** | GCP | `sc28_encryption.rego` | `compliance.sc28` | Ensures Cloud Storage buckets enforce encryption at rest. |
| **SC-28** | AWS | `sc28_encryption_aws.rego` | `compliance.sc28_aws` | Ensures S3 buckets have a matching `aws_s3_bucket_server_side_encryption_configuration`. |
| **AC-3** | GCP | `ac3_no_public.rego` | `compliance.ac3` | Prevents public ingress on GCP firewall rules. |
| **AC-3** | AWS | `ac3_no_public_aws.rego` | `compliance.ac3_aws` | Ensures S3 buckets have an `aws_s3_bucket_public_access_block` with all four flags set to `true`. |
| **CM-6** | GCP | `cm6_required_labels.rego` | `compliance.cm6` | Enforces required resource labels on GCP resources. |
| **CM-6** | AWS | `cm6_required_tags_aws.rego` | `compliance.cm6_aws` | Enforces required resource tags (`Project`, `Environment`, `ManagedBy`, `ComplianceScope`) on AWS resources. |