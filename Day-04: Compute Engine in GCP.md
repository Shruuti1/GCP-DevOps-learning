# Day-04: Compute Engine in GCP

## Topics Covered
- Compute Engine Basics
- Creating VM Instances
- SSH Access
- Installing NGINX
- Startup Scripts
- Firewall Rules
- Custom Images

---

# What is Compute Engine?

Compute Engine is GCP’s service for creating and managing Virtual Machines (VMs).

It allows us to:
- Launch Linux/Windows VMs
- Configure CPU and RAM
- Install applications
- Access servers using SSH

---

# Key Concepts

| Concept | Description |
|---|---|
| Instance | Virtual Machine |
| Zone | Data center location |
| Machine Type | CPU & RAM configuration |
| Boot Disk | OS storage |
| Firewall Rule | Controls network access |

---

# Tasks Completed

## Create VM Instance

```bash
gcloud compute instances create devops-vm \
--zone=us-central1-a \
--machine-type=e2-micro \
--image-family=ubuntu-2004-lts \
--image-project=ubuntu-os-cloud \
--tags=http-server
```

---

## Connect Using SSH

```bash
gcloud compute ssh devops-vm --zone=us-central1-a
```

---

## Install NGINX Manually

```bash
sudo apt update
sudo apt install -y nginx
sudo systemctl enable nginx
sudo systemctl start nginx
```

Test nginx:

```bash
curl http://localhost
```

---

## Create VM with Startup Script

```bash
gcloud compute instances create nginx-vm \
--zone=us-central1-a \
--machine-type=e2-micro \
--image-family=ubuntu-2004-lts \
--image-project=ubuntu-os-cloud \
--metadata startup-script='#! /bin/bash
apt update
apt install -y nginx
systemctl enable nginx
systemctl start nginx' \
--tags=http-server
```

---

## Create Firewall Rule

```bash
gcloud compute firewall-rules create allow-http \
--allow tcp:80 \
--target-tags=http-server
```

---

## Create Custom Image

```bash
gcloud compute instances stop nginx-vm --zone=us-central1-a
```

```bash
gcloud compute images create nginx-custom-image \
--source-disk=nginx-vm \
--source-disk-zone=us-central1-a
```

---

# Key Learnings

- Learned how to create VM instances
- Connected to VM using SSH
- Installed and managed NGINX
- Used startup scripts for automation
- Configured firewall rules
- Created reusable custom VM images

---
