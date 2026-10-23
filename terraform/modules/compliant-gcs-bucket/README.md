# compliant-gcs-bucket

A Terraform module that deploys a GCS bucket with a security baseline consumers cannot turn off.
It creates a customer-managed KMS keyring and key (SC-12), encrypts the bucket with that key using
GOOGLE_SYMMETRIC_ENCRYPTION and rotates the key every 90 days (SC-13, SC-28), enforces uniform
bucket-level access and public access prevention (AC-3), applies a retention policy with a
365-day minimum for prod validated at plan time (AU-11), and merges required compliance labels
on top of any consumer labels so they cannot be removed (CM-6). Versioning is always on.
Consumers set only business values: project, environment, retention, and name suffix.
The `compliance_attestation` output reports these controls in machine-readable form.
