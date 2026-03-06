
# Repository Configuration in OCI OS Management Hub

## Overview

Software repositories provide the packages required to install, update, and maintain the operating system on Oracle Linux instances. In Oracle Cloud Infrastructure (OCI), OS Management Hub allows administrators to centrally manage and control repository access for compute instances.

By managing repositories through OS Management Hub, administrators can ensure that all managed instances use approved and consistent software sources.

---

## What are Software Sources?

In OS Management Hub, repositories are referred to as **Software Sources**. These sources contain packages and updates for Oracle Linux systems.

Typical software sources include:

- Oracle Linux BaseOS
- Oracle Linux AppStream
- Oracle Linux Security Updates
- Custom repositories

These repositories act as the package source used during patch updates.

---

## Why Repository Configuration is Important

Proper repository configuration provides several benefits:

- Ensures consistent package versions across systems
- Prevents installation of unapproved packages
- Improves security by controlling update sources
- Simplifies patch management operations

Centralized repository management helps maintain stability and compliance across multiple compute instances.

---

## Repository Configuration Workflow

The following steps demonstrate how repository configuration works in OS Management Hub.

### Step 1 – Navigate to OS Management Hub

Login to the OCI Console and navigate to:

Menu → OS Management Hub


---

### Step 2 – Open Software Sources

Inside OS Management Hub:

1. Click **Software Sources**
2. View the available repositories
3. Identify the required repositories for your environment

Examples include Oracle Linux BaseOS and security update repositories.

---

### Step 3 – Attach Repository to Managed Instance

Repositories must be attached to managed instances so they can retrieve packages.

Steps:

1. Open **Managed Instances**
2. Select the target compute instance
3. Attach the required software sources

Once attached, the instance can download packages from those repositories.

---

### Step 4 – Repository Usage During Updates

When patch updates are triggered, the Oracle Cloud Agent running on the compute instance retrieves packages from the configured repositories.

Example command executed internally on the instance:

```bash
sudo dnf update

