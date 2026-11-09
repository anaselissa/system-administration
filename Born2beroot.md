*This project has been created as part of the 42 curriculum by aaleassa.*

# Born2beroot

## Description

Born2beroot is a system administration project focused on installing, configuring, and securing a Linux server inside a virtual machine.

The project introduces essential concepts of virtualization, Linux system administration, user and permission management, network security, and automated system monitoring.

For this project, I configured a minimal **Debian 13 (Trixie)** environment using **Oracle VirtualBox**.

## System Overview

| Component | Configuration |
|---|---|
| Operating System | Debian GNU/Linux 13 (Trixie) |
| Virtualization | Oracle VirtualBox |
| Hostname | `aaleassa42` |
| Storage | Encrypted LVM |
| SSH | Port `4242`, root login disabled |
| Firewall | UFW enabled, only port `4242` allowed |
| Security Module | AppArmor |
| Monitoring | Bash script scheduled with cron |

## Main Configuration

### 1. Virtualization and Storage

The system runs inside a VirtualBox virtual machine, providing an isolated environment for installing and managing the operating system.

The disk uses encrypted storage with **Logical Volume Manager (LVM)**.

The main logical volumes are:

- `/` — Root filesystem.
- `/home` — User home directories.
- `swap` — Swap space.

LVM provides flexible storage management, while encryption helps protect data stored on the virtual disk.

### 2. Users and Password Policy

A non-root user, `aaleassa`, is configured with the `sudo` and `user42` groups.

The password policy enforces:

- Minimum password length of 10 characters.
- At least one uppercase letter, lowercase letter, and digit.
- No more than three consecutive identical characters.
- Passwords cannot contain the username.
- Password expiration after 30 days.
- Minimum of 2 days between password changes.
- A 7-day warning before expiration.

### 3. Sudo Configuration

Sudo allows authorized users to execute commands with elevated privileges without directly logging in as root.

The configuration includes:

- Maximum of three password attempts.
- Custom incorrect-password message.
- Logging of sudo commands and input/output.
- TTY requirement.
- Restricted `secure_path`.

Sudo activity is logged under `/var/log/sudo/`.

### 4. SSH and Firewall

**SSH** provides secure remote access to the server.

It is configured to:
- Listen on port `4242`.
- Disable direct root login.

**UFW (Uncomplicated Firewall)** manages incoming network traffic. It is enabled and configured to allow only port `4242`.

For local testing, VirtualBox forwards host port `4241` to guest port `4242`.

### 5. AppArmor

AppArmor is a Linux security module that implements mandatory access control through application profiles.

It helps restrict the resources and operations available to individual applications.

AppArmor is enabled in this Debian environment.

### 6. System Monitoring

The `monitoring.sh` Bash script collects and displays system information, including:

- Operating system architecture and kernel.
- Physical and virtual CPU counts.
- RAM and disk usage.
- CPU load.
- Last system boot.
- LVM usage.
- Established TCP connections.
- Logged-in users.
- Network IP and MAC addresses.
- Number of sudo commands.

The script is scheduled through cron to run every 10 minutes. It uses `wall` to broadcast the report to logged-in terminal sessions.

## Technical Choices

### Debian vs. Rocky Linux

Both Debian and Rocky Linux are suitable for server environments.

- **Debian:** Known for its stability, extensive documentation, and APT package management.
- **Rocky Linux:** An enterprise-oriented distribution compatible with Red Hat Enterprise Linux.

Debian was selected for this project because of its stability and package-management ecosystem.

### AppArmor vs. SELinux

Both provide mandatory access control.

- **AppArmor:** Uses application-specific security profiles.
- **SELinux:** Uses security labels and policies to control access across the system.

AppArmor was used because it is the default security module in Debian.

### UFW vs. firewalld

Both tools manage firewall rules.

- **UFW:** Provides a straightforward interface for configuring firewall rules.
- **firewalld:** Provides dynamic firewall management through zones and services.

UFW was selected for its simplicity and suitability for this project's requirements.

### VirtualBox vs. UTM

Both tools allow users to run virtual machines.

- **VirtualBox:** A cross-platform virtualization solution with broad operating system support.
- **UTM:** A virtualization and emulation application commonly used on macOS.

VirtualBox was used to create and manage the Debian virtual machine.

## What I Learned

Through Born2beroot, I gained practical experience with:

- Installing and configuring a Linux server.
- Managing users, groups, permissions, and privileges.
- Working with encrypted storage and LVM.
- Configuring SSH and firewall rules.
- Understanding Linux security mechanisms.
- Automating tasks using Bash and cron.
- Monitoring system resources and inspecting logs.

## Resources

- [Born2beroot Project Subject](https://www.42network.org/)
- [Every Linux Distro Explained in 4 Minutes](https://youtu.be/VKNMI6cYOFk?si=adjDOhPSs3vfLLBm)
- [Virtual Machines Explained in 15 Minutes](https://youtu.be/mQP0wqNT_DI?si=Lm4YU1qsSVDdEiYX)
- [Introduction to LVM | Linux Academy](https://youtu.be/dMHFArkANP8?si=-ly6kmJ6W5Mwrim7)

## Use of AI

AI tools were used as learning and support resources to clarify Linux concepts, understand configuration options, and troubleshoot issues.

The system configuration and project work were carried out and reviewed by me.

---

**Note:** This repository contains the project documentation and related files. The virtual machine disk itself is not included.
