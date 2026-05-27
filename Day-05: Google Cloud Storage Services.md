# Day-05: Google Cloud Storage Services

## Topics Covered
- Cloud Storage (GCS)
- Filestore
- Local SSD
- Bigtable
- Pub/Sub

---

# Google Cloud Storage Services

| Service | Purpose |
| Cloud Storage | Store files, backups, logs, artifacts |
| Filestore | Shared file storage for VMs/GKE |
| Local SSD | High-speed temporary storage |
| Bigtable | NoSQL database for large-scale data |
| Pub/Sub | Messaging and event streaming |

---

# DevOps Use Cases

## Cloud Storage (GCS)
- Store CI/CD artifacts
- Store backups and logs
- Terraform state storage

## Filestore
- Shared storage for Kubernetes apps
- Jenkins shared data

## Local SSD
- Fast temporary cache
- Build pipeline acceleration

## Bigtable
- Monitoring and observability data
- Time-series workloads

## Pub/Sub
- Trigger automation workflows
- Event-driven architecture
- Log streaming and alerts

---

# Hands-On Demo

## 1. Create a GCS Bucket

Steps:
- Open Cloud Storage → Buckets
- Create a new bucket
- Upload a sample file (`hello.txt`)

---

## 2. Create Service Account

Steps:
- IAM & Admin → Service Accounts
- Create service account:
  `gcs-demo-sa`
- Assign role:
  `Storage Object Admin`

---

## 3. Create Compute Engine VM

Steps:
- Compute Engine → VM Instances
- Create VM:
  `gcs-demo-vm`
- Attach created service account

---

## 4. Access Bucket from VM

SSH into VM and run:

```bash
gcloud storage ls
```

Download file:

```bash
gcloud storage cp gs://BUCKET_NAME/hello.txt .
```

Upload file:

```bash
gcloud storage cp test.txt gs://BUCKET_NAME/
```

---

# Cleanup

Delete:
- VM Instance
- GCS Bucket
- Service Account

---

# Key Learnings

- Learned different GCP storage services
- Connected GCS with Compute Engine
- Used Service Accounts for secure access
- Uploaded and downloaded files from VM

---

# Day-05: GCS with VM

## Tasks Completed
- Created GCS Bucket
- Created Service Account
- Created Compute Engine VM
- Connected VM with GCS
- Uploaded & Downloaded files

## Commands Used

```bash
gcloud storage ls gs://BUCKET_NAME
```

```bash
gcloud storage cp gs://BUCKET_NAME/hello.txt .
```

```bash
gcloud storage cp vm-upload.txt gs://BUCKET_NAME/
```

## Key Learnings
- Learned GCS basics
- Used Service Accounts securely
- Accessed Cloud Storage from VM

---
