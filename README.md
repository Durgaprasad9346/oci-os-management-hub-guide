# oci-os-management-hub-guide


## Overview

OS Management Hub is a service in Oracle Cloud Infrastructure that helps administrators centrally manage operating system updates, security patches, and software repositories for Oracle Linux compute instances.

Using OS Management Hub, administrators can monitor system updates, configure repositories, schedule patch operations, and manage package updates across multiple instances from a single interface.

This repository explains the architecture, core components, and operational workflow of OS Management Hub in OCI.

# Core Components

OS Management Hub works with several OCI components to manage operating system updates and packages across compute instances.

## 1. OS Management Hub Service

OS Management Hub is the central service used to manage operating system updates and package lifecycle for Oracle Linux instances in OCI.

It provides capabilities such as:

- Centralized patch management
- Package update orchestration
- Repository configuration
- Patch scheduling
- Package exclusion
- Update compliance monitoring

Administrators can manage all patch operations from the OCI console.

---

## 2. Oracle Cloud Agent

Oracle Cloud Agent is a lightweight management agent installed on OCI compute instances.

It enables communication between the compute instance and OCI services.

For OS Management Hub, the agent performs the following tasks:

- Registers compute instances with OS Management Hub
- Executes patch operations
- Collects system information
- Reports update status back to OCI

The OS Management Hub plugin must be enabled within Oracle Cloud Agent for patch management to work.

---

## 3. Managed Instances

Managed instances are compute instances that are registered with OS Management Hub.

Once registered, administrators can perform operations such as:

- Apply patch updates
- Install or remove packages
- Monitor update compliance
- Schedule patch operations

These instances are managed centrally from the OCI console.

---

## 4. Software Sources (Repositories)

Software sources are repositories that contain operating system packages and updates.

OS Management Hub allows administrators to attach repositories to managed instances.

Common repositories include:

- Oracle Linux Base OS Updates
- Security Updates
- Application Stream repositories

Managing repositories centrally ensures consistency across all instances.

---

## 5. Instance Groups

Instance groups allow administrators to organize compute instances into logical groups.

Examples include:

- Production servers
- Development servers
- Test environments

Using instance groups allows patch updates to be applied to multiple instances simultaneously.


# Security and Compliance Considerations

Maintaining secure and compliant infrastructure is a critical aspect of system administration. OS Management Hub helps organizations maintain operating system security and compliance by ensuring that systems receive the latest security updates and patches.

## Centralized Patch Management

By managing updates from a centralized service, administrators can ensure that all compute instances receive necessary security patches in a controlled and consistent manner.

This reduces the risk of vulnerabilities caused by outdated software packages.

---

## Controlled Repository Access

OS Management Hub allows administrators to control which repositories are available to compute instances.

This prevents systems from installing untrusted packages and ensures that updates are obtained only from approved and secure repositories.

---

## Scheduled Maintenance Windows

Using scheduled patch operations allows organizations to apply updates during predefined maintenance windows. This helps minimize operational impact while ensuring systems remain secure and up to date.

---

## Package Exclusion for Stability

In some production environments, certain packages must remain at a specific version to maintain application compatibility.

OS Management Hub allows administrators to exclude selected packages from update operations to avoid unintended system changes.

---

## Compliance Visibility

Administrators can monitor update status and package compliance across all managed instances through the OCI console.

This centralized visibility helps organizations maintain compliance with security policies and operational standards.


## Additional Documentation

- [Patch Management Workflow](docs/patch-management-workflow.md)
- [Repository Configuration](docs/repository-configuration.md)
- [Patch Scheduling and Package Exclusion](docs/scheduling-and-package-exclusion.md)
