````markdown id="t9x2mv"
# Day-02: GCP Project Setup and Billing

## Topics Covered
- GCP Project Basics
- Billing Accounts
- Budget Alerts
- Enabling APIs

---

# Understanding GCP Projects

In GCP, everything runs inside a project.

Examples:
- VM instances
- Storage buckets
- Databases
- Cloud Run services

A project helps organize resources, billing, and permissions.

---

# Billing in GCP

When creating a GCP account, a billing account is automatically created.

Important points:
- One billing account can manage multiple projects
- Budget alerts help avoid unexpected charges
- Charges apply only after free credits are exhausted

---

# Tasks Completed

## 1. Created a New Project

Steps:
- Open GCP Console
- Click project dropdown
- Click **New Project**
- Created project: `gcp-zero-to-hero`

---

## 2. Set Budget Alerts

Configured budget alerts for:
- 50%
- 90%
- 100%

This helps monitor cloud spending.

---

## 3. Enabled Required APIs

Enabled:
- Compute Engine API
- Cloud Storage API
- Cloud Monitoring API
- Cloud Logging API
- IAM API

Commands used:

```bash
gcloud services enable compute.googleapis.com \
storage.googleapis.com \
monitoring.googleapis.com \
logging.googleapis.com \
cloudresourcemanager.googleapis.com \
iamcredentials.googleapis.com
```

---

# Key Learnings

- Understood GCP project structure
- Learned how billing works in GCP
- Configured budget alerts
- Enabled APIs required for cloud services

---
````
