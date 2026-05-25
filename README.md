# CI/CD Best Practices — Terraform Infrastructure
## Architecture
 
This repository manages shared infrastructure resources:
- **S3 Bucket** — Versioned artifact storage with encryption and lifecycle policies
- **DynamoDB Table** — Application state store with point-in-time recovery
 
## CI/CD Workflows
 
| Workflow | Trigger | Purpose |
|----------|---------|---------|
| CI Pipeline | PR to `main` | Format, validate, security scan, plan |
| CD Pipeline | Push to `main` | Plan + deploy with manual approval |
| Commit Lint | PR open/edit | Enforce conventional commit titles |
| Release Please | Push to `main` | Automated versioning and changelog |
 
## Quick Start
 
```bash
cd terraform
terraform init
terraform plan
terraform apply