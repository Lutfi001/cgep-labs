# Compliance Policies (NIST 800-53)

Automated Policy-as-Code rules evaluated against Terraform plan JSON using Open Policy Agent (OPA).

| Policy File | Control ID | Severity | Remediation |
| :--- | :--- | :--- | :--- |
| `policies/sc28_encryption.rego` | **SC-28** | High | Add an `encryption { default_kms_key_name = ... }` block referencing a `google_kms_crypto_key` you control. |
| `policies/ac3_no_public.rego` | **AC-3** | Critical | Set `uniform_bucket_level_access = true` and `public_access_prevention = "enforced"`. For firewalls, narrow `source_ranges` or remove the rule. |
| `policies/cm6_required_tags.rego` | **CM-6** | Medium | Add the four required labels (`project`, `environment`, `managed_by`, `compliance_scope`) to the resource. |