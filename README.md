# Terraform Infrastructure for PriorityCloud

This repository contains reusable and environment-specific Terraform configurations to provision and manage cloud infrastructure on AWS.

---

## 📦 Repository Structure

```
terraform-infra/
├── modules/              # Reusable infrastructure modules
│   ├── ec2/              # EC2 instance module
│   ├── vpc/              # VPC and subnets
│   ├── alb/              # Load balancer (optional)
│   └── ...               # More modules as needed
├── envs/                 # Environment-specific configs
│   ├── dev/              # Development environment
│   └── prod/             # Production (future)
├── backend.tf            # Remote state backend config (S3 + DynamoDB)
├── .gitignore
└── README.md
```

---

## 🚀 Getting Started

### Prerequisites

- AWS CLI with valid credentials (`~/.aws/credentials`)
- Terraform v1.5 or later
- A configured SSH key (for EC2 access)
- IAM Role/User with appropriate permissions (EC2, VPC, S3, DynamoDB)

---

### 🔧 Initialize Terraform

```bash
cd envs/dev
terraform init
terraform plan
```

---

## 🔐 Remote State (Coming Soon)

This repo will use:

- **S3** for state file storage
- **DynamoDB** for state locking

---

## 🤖 CI/CD with Jenkins (Coming Soon)

A Jenkins pipeline will be used to automatically:

- Validate Terraform syntax
- Run `terraform plan`
- Optionally apply infrastructure changes

---

## 🧱 Modules

Each module (e.g., `ec2`, `vpc`) is self-contained and reusable across environments.

---

## ✍️ Contribution

Feel free to fork this repo or raise pull requests if you'd like to improve or extend functionality.

---

## 📜 License

MIT License
