
# Patch Scheduling and Package Exclusion in OCI OS Management Hub

## Overview

OS Management Hub in Oracle Cloud Infrastructure (OCI) allows administrators to automate patch management by scheduling updates and controlling which packages should be updated. This helps organizations maintain system security while minimizing operational disruptions.

Two important capabilities provided by OS Management Hub are:

- Patch Scheduling
- Package Exclusion

These features allow administrators to control when updates occur and which packages should be skipped during patch operations.

---

## Patch Scheduling

Patch scheduling allows administrators to automatically apply updates to compute instances during predefined maintenance windows. This ensures that systems remain up to date without requiring manual intervention.

Using scheduled patch operations helps maintain consistent patching across environments such as production, development, and testing.

### Common Scheduling Strategies

Organizations often implement patch schedules such as:

- Weekly security patch updates
- Monthly maintenance updates
- Scheduled updates for development environments

Scheduling ensures that patch updates are applied at predictable times, reducing the risk of unexpected downtime.

---

## Patch Scheduling Workflow

The following steps demonstrate how patch scheduling works in OS Management Hub.

### Step 1 – Navigate to OS Management Hub

Login to the OCI Console and navigate to:

Menu → OS Management Hub

---

### Step 2 – Select Managed Instances or Instance Group

Administrators can apply patch schedules to:

- Individual compute instances
- Instance groups

Instance groups are commonly used to schedule updates across multiple systems.

---

### Step 3 – Create a Patch Schedule

Define a patch schedule by specifying:

- Update frequency
- Maintenance window
- Target instances or instance groups

This configuration allows patch operations to execute automatically during scheduled periods.

---

### Step 4 – Patch Execution

At the scheduled time, OS Management Hub triggers the patch operation.

The Oracle Cloud Agent running on the compute instance executes the package update using the system package manager.

Example command executed on the instance:

```bash
sudo dnf update
