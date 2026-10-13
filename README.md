# 🐧 Enterprise Linux System Administration Lab

A hands-on Linux system administration project built using **VMware Workstation and Red Hat Enterprise Linux (RHEL 10)**. This lab simulates a multi-server environment focused on storage management, access control, security hardening, web hosting, and backup operations.

## 📐 Lab Architecture & Topology

- **Production Server — RedHat1 (`192.168.242.131`):** Hosts the Apache web server, LVM-backed web content, user access controls, security configurations, and scheduled backup scripts.
- **Backup Server — RedHat2 (`192.168.242.132`):** Receives backup archives over SSH/SCP and provides separate storage for backup files.

The two virtual machines communicate over a VMware virtual network, enabling remote administration and inter-server file transfers.

## 🛠 Key Implemented Features

### 1. Storage Management with LVM
- Created the `vg_data` volume group using two physical volumes.
- Created the `lv_app` logical volume and mounted it at `/data/html`.
- Configured the XFS filesystem and verified storage allocation using `pvs`, `vgs`, `lvs`, and `df -h`.
- Verified the available capacity within the volume group for potential future expansion.

### 2. User and Access Management
- Configured user groups and POSIX Access Control Lists (ACLs) for shared directory access.
- Applied default ACLs and the sticky bit to `/data/shared`.
- Configured restricted passwordless sudo permissions for selected Apache service-management commands.

### 3. Security and Firewall Configuration
- Configured SELinux file contexts for the custom web content directory.
- Managed firewall services for SSH, HTTP, and HTTPS.
- Configured access-control settings to support restricted administrative privileges and secure web content access.

### 4. Apache Web Server
- Installed and enabled the Apache HTTP Server (`httpd`).
- Configured the custom web content directory at `/data/html`.
- Verified that the Apache service was active and running.

### 5. Backup Scheduling and Inter-Server Transfer
- Configured Cron jobs for scheduled maintenance and backup tasks.
- Created a Bash script to generate compressed data backup archives.
- Transferred backup archives from the production server to the backup server using SSH/SCP.

## 📸 Lab Visuals & Evidence

The repository includes architecture diagrams and terminal screenshots documenting:

- LVM configuration and filesystem mounts.
- User permissions, ACLs, and restricted sudo access.
- SELinux contexts and firewall configuration.
- Apache service status.
- Cron scheduling and backup archive creation.
- Successful inter-server file transfers using SCP.

## 🎯 Learning Objectives

- Apply practical Linux system administration concepts in a virtualized environment.
- Manage logical volumes, filesystems, users, groups, and permissions.
- Configure Linux security controls and web services.
- Automate routine tasks using Bash scripts and Cron.
- Practice transferring backup archives between Linux servers.

## 🧰 Technologies Used

- Red Hat Enterprise Linux 10
- VMware Workstation
- Apache HTTP Server
- LVM and XFS
- SELinux
- Firewalld
- Bash Scripting
- Cron
- SSH and SCP
- POSIX ACLs

---

**Project Focus:** Practical Linux administration, server security, storage management, and backup operations.
