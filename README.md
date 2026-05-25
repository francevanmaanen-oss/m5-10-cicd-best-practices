# CI/CD Best Practices — Terraform Infrastructure
 
![CI Pipeline](https://github.com/YOUR_USERNAME/ce-lab-cicd-best-practices/actions/workflows/ci.yml/badge.svg)
![CD Pipeline](https://github.com/YOUR_USERNAME/ce-lab-cicd-best-practices/actions/workflows/cd.yml/badge.svg)
![Commit Lint](https://github.com/YOUR_USERNAME/ce-lab-cicd-best-practices/actions/workflows/commit-lint.yml/badge.svg)
![Release](https://github.com/YOUR_USERNAME/ce-lab-cicd-best-practices/actions/workflows/release.yml/badge.svg)
 
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