# Day-03: GCP IAM Fundamentals

## Topics Covered
- What is IAM?
- IAM Roles
- IAM Policy Hierarchy
- Service Accounts
- IAM Best Practices

---

# What is IAM?

IAM (Identity and Access Management) controls:

> Who can access what resources and what actions they can perform.

Formula:

```text
Who → Can do what → On which resource
```

IAM helps secure cloud resources in GCP.

---

# Core IAM Components

| Component | Description |
|---|---|
| Identity | User, group, or service account |
| Role | Collection of permissions |
| Policy | Binding between identity and role |
| Resource | VM, bucket, project, etc. |

---

# Types of IAM Roles

| Role Type | Example |
|---|---|
| Basic Roles | Owner, Editor, Viewer |
| Predefined Roles | roles/storage.admin |
| Custom Roles | Custom permissions |

> Predefined and Custom roles are recommended over Basic roles.

---

# IAM Hierarchy

Permissions can be assigned at:
- Organization
- Folder
- Project
- Resource

Permissions inherit from parent resources.

---

# Service Accounts

Service accounts are non-human identities used by:
- Applications
- CI/CD pipelines
- Automation scripts

Example:
Cloud Build using a service account to deploy applications.

---

# IAM Best Practices

- Follow Least Privilege principle
- Avoid Owner/Editor roles
- Use Service Accounts for automation
- Rotate secrets and keys regularly
- Audit IAM permissions frequently

---

# Hands-On Commands

## Create Project

```bash
export PROJECT_ID="devops-iam-demo-$(date +%s)"
gcloud projects create $PROJECT_ID
gcloud config set project $PROJECT_ID
```

---

## Assign Viewer Role

```bash
gcloud projects add-iam-policy-binding $PROJECT_ID \
--member="user:example@gmail.com" \
--role="roles/viewer"
```

---

## Create Service Account

```bash
gcloud iam service-accounts create devops-bot \
--display-name="DevOps Pipeline Bot"
```

---

# Key Learnings

- Learned IAM basics in GCP
- Understood roles and permissions
- Explored IAM hierarchy
- Learned about Service Accounts
- Practiced IAM commands using gcloud

---
