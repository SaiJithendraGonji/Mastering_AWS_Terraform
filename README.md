# 🏗️ Mastering AWS with Terraform

> Production-ready, reusable Terraform modules for AWS infrastructure — built from real-world patterns across enterprise deployments at OneAdvanced, GlobalLogic, Infosys (Unilever UK, Cummins UK), and early cloud engineering roles.

These aren't tutorial modules. They reflect the IaC patterns used to manage 15+ AWS accounts, cut deployment time from days to hours, and achieve 95% code reusability across innovation, non-prod, pre-prod, and production environments.

---

## 📦 Modules

### Networking
```
modules/networking/
├── vpc/              # Multi-tier VPC with public/private/data subnets
├── transit-gateway/  # Cross-account Transit Gateway with automated peering
├── vpc-peering/      # Automated VPC peering configurations
└── waf/              # WAF rules with automated threat intelligence updates
```

### Compute
```
modules/compute/
├── eks/              # EKS cluster with managed node groups + Karpenter
├── ecs-fargate/      # ECS Fargate with ALB, task definitions, auto scaling
├── ec2/              # EC2 with golden AMI pipeline + automated patching
└── lambda/           # Lambda with IAM, VPC, and dead-letter queue config
```

### Storage & Data
```
modules/storage/
├── rds/              # RDS PostgreSQL/MySQL with Multi-AZ, automated backups
├── s3/               # S3 with versioning, lifecycle policies, bucket policies
├── dynamodb/         # DynamoDB with autoscaling and point-in-time recovery
└── elasticache/      # Redis/Memcached cluster configuration
```

### Security & Identity
```
modules/security/
├── iam/              # IAM roles, policies, instance profiles (least privilege)
├── kms/              # KMS key management for encryption at rest
├── secrets-manager/  # AWS Secrets Manager with automated rotation
└── config-rules/     # Custom AWS Config rules for compliance drift detection
```

### Observability
```
modules/observability/
├── cloudwatch/       # Dashboards, alarms, log groups, metric filters
├── cloudwatch-alarms/# Automated alarm lifecycle management (removed 200K+ redundant alarms)
└── sns/              # SNS topics with Slack integration for cost anomaly alerts
```

---

## 🎯 Key Features

- **95%+ code reusability** through modular design — write once, deploy everywhere
- **Multi-environment support** — single module set covers dev, non-prod, pre-prod, production
- **Remote state management** — S3 backend with DynamoDB state locking
- **Automated testing** — Terratest integration with 95% test coverage
- **Cost controls built in** — resource tagging enforcement, scheduled scaling for non-prod
- **Security by default** — encryption at rest/transit, least-privilege IAM, no public resources without explicit opt-in
- **Drift detection** — AWS Config rules catch infrastructure changes made outside Terraform

---

## 💰 Real Savings Delivered

Using these patterns at OneAdvanced:

| Initiative | Annual Saving |
|-----------|--------------|
| Removed 200,000+ redundant CloudWatch alarms | $175,000 |
| Spot instance management for non-critical workloads | $70,000 |
| Automated resource scheduling (non-prod) | $50,000 |
| **Total** | **$285,000** |

---

## 📁 Repository Structure

```
├── modules/                    # Reusable module library
│   ├── networking/
│   ├── compute/
│   ├── storage/
│   ├── security/
│   └── observability/
├── environments/
│   ├── dev/
│   ├── non-prod/
│   ├── pre-prod/
│   └── production/
├── tests/                      # Terratest test suites
│   ├── vpc_test.go
│   ├── eks_test.go
│   └── rds_test.go
├── scripts/
│   └── boto3/                  # Python automation for AWS lifecycle management
└── docs/
    ├── architecture/           # Architecture decision records (ADRs)
    └── runbooks/
```

---

## 🛠️ Tech Stack

![Terraform](https://img.shields.io/badge/Terraform-7B42BC?style=flat&logo=terraform&logoColor=white)
![AWS](https://img.shields.io/badge/AWS-FF9900?style=flat&logo=amazon-aws&logoColor=white)
![Python](https://img.shields.io/badge/Python-3776AB?style=flat&logo=python&logoColor=white)
![Go](https://img.shields.io/badge/Go-00ADD8?style=flat&logo=go&logoColor=white)
![GitHub Actions](https://img.shields.io/badge/GitHub_Actions-2088FF?style=flat&logo=github-actions&logoColor=white)

---

## 🌍 Real-World Context

| Organisation | What was built |
|-------------|----------------|
| OneAdvanced UK | Enterprise-wide IaC across AWS + Azure, 15+ accounts, $285K cost savings |
| GlobalLogic UK | EKS + ECS Fargate for FinTech insurance platform (100K+ policies/day) |
| Infosys → Unilever UK | EKS + ECS infrastructure, Terraform-based VPC architectures |
| Infosys → Cummins UK | Azure + AWS hybrid IaC across dev/staging/production |

---

## 📖 Related

- [ENDTOEND_DEVSECOPS](https://github.com/SaiJithendraGonji/ENDTOEND_DEVSECOPS) — CI/CD pipeline that scans and deploys this infrastructure
- [HELM-Charts](https://github.com/SaiJithendraGonji/HELM-Charts) — Kubernetes workloads running on these clusters
