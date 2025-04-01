# Hidden Sudo User Setup

## Overview
Create a dedicated, hidden administrative user to manage system services securely without relying on default accounts.

## User Details
- **Username:** Choose your own `<admin-username>`
- **Permissions:** Full `sudo` access
- **Purpose:** Used for running monitoring, logging, and automation services
- **Visibility:** Hidden from login screens and standard user lists

## User Creation Steps

### 1. Create the Admin User

Replace `<admin-username>` with your preferred username:

```bash
sudo useradd -m -s /bin/bash <admin-username>
```

###  Set a Password for <admin-username>

```bash
sudo passwd <admin-username>
```
(You'll be prompted to set a password.)

###  Give <admin-username> Sudo Privileges
```bash
sudo usermod -aG sudo <admin-username>
```
 This allows the new admin account to run commands as root when needed.

## Security Considerations
- This account is only used for running services and administration.
- Regular user accounts do not have access to modify or interact with this user.
- Password authentication is disabled; only key-based access is allowed.
