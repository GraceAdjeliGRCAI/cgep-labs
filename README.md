# cgep-labs

CGE-P (Cloud Governance Engineering Practitioner) certification labs — compliance as code, built and maintained by Grace M. Adjeli.

This repository contains hands-on Terraform implementations and captured compliance evidence for each lab in the CGE-P curriculum.

## Structure

- `terraform/primitives/` — standalone infrastructure units deployed directly
- `terraform/modules/` — reusable Terraform modules (introduced in later labs)
- `scripts/` — shared automation scripts
- `evidence/` — captured compliance evidence (plan.json, state.json) per lab, named by lab number

## Labs completed

- **Lab 2.3** — Compliant S3 bucket enforcing SC-28, AU-3, AU-6, CM-6, AC-3 (`terraform/primitives/compliant-s3/`)
