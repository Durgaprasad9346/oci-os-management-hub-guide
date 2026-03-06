# Patch Management Workflow in OCI OS Management Hub

## Overview

Patch management is an important process for maintaining the security and stability of operating systems. OS Management Hub in Oracle Cloud Infrastructure (OCI) provides a centralized platform to manage operating system updates, apply security patches, and maintain package versions across multiple Oracle Linux compute instances.

This document explains how patch updates are performed using OS Management Hub.

---

## Patch Management Architecture Flow

Administrator initiates patch updates from the OCI Console. The request is processed by OS Management Hub, which communicates with the Oracle Cloud Agent running on the compute instance. The agent then executes the package update using the system package manager.



---

## Step 1 – Instance Registration

Before patch management can begin, compute instances must be registered with OS Management Hub.

Requirements:

- Oracle Linux compute instance
- Oracle Cloud Agent installed
- OS Management Hub plugin enabled

When the Oracle Cloud Agent plugin is enabled, the instance automatically registers with OS Management Hub and appears as a **Managed Instance** in the OCI Console.

---

## Step 2 – Repository Configuration

Software repositories provide the packages required for operating system updates.

Administrators must attach appropriate repositories to managed instances.

Common repositories include:

- Oracle Linux BaseOS repository
- Oracle Linux AppStream repository
- Security update repositories

These repositories act as the source for operating system updates and security patches.

---

## Step 3 – Instance Grouping

To simplify management, instances can be organized into **Instance Groups**.

Examples:

- Production Servers
- Development Servers
- Test Environments

Grouping instances allows administrators to apply updates to multiple systems simultaneously.

---

## Step 4 – Initiating Patch Updates

Patch updates can be triggered directly from the OCI Console.

Steps:

1. Navigate to **OS Management Hub**
2. Open **Managed Instances**
3. Select the target instance or instance group
4. Click **Update All Packages**

OS Management Hub sends the update request to the Oracle Cloud Agent running on the instance.

---

## Step 5 – Patch Execution on the Instance

The Oracle Cloud Agent executes the patch update on the compute instance.

Internally, the update operation runs the system package manager.

Example command executed on the instance:

```bash
sudo dnf update
