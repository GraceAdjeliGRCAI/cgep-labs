# compliant-s3

This module enforces SC-28, AU-3, AU-6, CM-6, and AC-3 on a single S3 bucket.

| Control | Implementation |
|---------|---------------|
| SC-28   | AES-256 server-side encryption on both primary and log buckets |
| AU-3    | S3 server access logging enabled, shipping to a dedicated log bucket |
| AU-6    | Log bucket retains access records for audit review |
| CM-6    | Required compliance tags applied via provider default_tags |
| AC-3    | All four public access block flags set to true on both buckets |

## Usage

```hcl
module "compliant_s3" {
  source       = "./terraform/primitives/compliant-s3"
  project_name = "cgep-lab"
  environment  = "dev"
}
```

## Outputs

- `bucket_arn` — ARN of the primary data bucket
- `bucket_name` — Name of the primary data bucket  
- `log_bucket_arn` — ARN of the log bucket
- `encryption_algorithm` — SC-28 attestation (AES256)
