# Project: Secure WordPress Web Server with Database Backup and Vault Integration

## Overview

This project sets up a secure web server hosting a WordPress site with a dedicated database server. The infrastructure is designed with best practices for security, automated backups, and password management using Vault.

---

## Features

1. **Web Server with WordPress**:
   - A fully functional WordPress installation hosted on a dedicated server.
   - Accessible via a custom domain: `www.instaXX.local`.

2. **Secure Networking with IPTables**:
   - Only HTTP (port 80) and SSH (port 22) traffic are allowed.
   - All other traffic is blocked for enhanced security.

3. **Database Server**:
   - A separate server is configured for hosting the WordPress database.
   - Database credentials are securely stored and managed in Vault.

4. **Automated Database Backups**:
   - Daily local backups of the database are scheduled at `01:00 AM`.

5. **DNS Configuration**:
   - DNS records updated to route traffic to the WordPress site using the `www.instaXX.local` domain.

6. **Playbook Accessibility**:
   - The playbook can be executed from any client machine within the organization's network.

---

## Technical Details

- **Configuration Management**: Ansible
  - Organized variables for scalability and readability.
  - Utilizes community roles from Ansible Galaxy for common tasks.

- **Roles**:
  - **System Role**: Configures system-specific settings and security measures.

- **Vault Integration**:
  - Passwords for the database are securely stored and retrieved from Vault during deployment.

- **Backup Implementation**:
  - Cron job ensures daily backups of the database are stored locally.

---

## Usage

### Prerequisites

1. **Ansible** installed on the client machine.
2. **Vault** setup and configured for storing database credentials.
3. Proper DNS configuration for `www.instaXX.local`.

### Deployment Steps

1. Clone the repository:
   ```bash
   git clone <repository_url>
   cd <repository_folder>
