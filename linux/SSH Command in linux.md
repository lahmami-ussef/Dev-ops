# SSH Command in Linux: Cheat Sheet



## 1. Summary

**SSH (Secure Shell)** is a protocol to access and control a remote computer over a network. Unlike Telnet or Rlogin, it **encrypts all data** (credentials and commands). It uses **TCP port 22** by default and is supported by all major Linux distributions.

---

## 2. Syntax

```bash
ssh [username]@[hostname or IP address]
```

Example:

```bash
ssh vboxuser@10.0.2.15
```

---

## 3. Installation (OpenSSH)

| Distro | Command | Definition |
|--------|---------|------------|
| Ubuntu/Debian | `sudo apt update` | Refreshes the package list. |
| Ubuntu/Debian | `sudo apt install openssh-client openssh-server` | Installs the SSH client and server. |
| CentOS/Fedora/RHEL | `sudo dnf install openssh-clients openssh-server` | Installs the SSH client and server. |
| All | `sudo systemctl start sshd` | Starts the SSH service. |
| All | `sudo systemctl enable sshd` | Starts SSH automatically at boot. |
| All | `sudo systemctl status sshd` | Checks whether the service is running. |

---

## 4. Examples

### Example 1: Connect to a remote server

```bash
ssh vboxuser@10.0.2.15
```

- On first connection, SSH asks you to verify the server fingerprint: type `yes`, press Enter, then enter the password.
- Once authenticated, you can run commands as in a local terminal.

### Example 2: Key authentication (more secure than passwords)

| Step | Command | Definition |
|------|---------|------------|
| 1 | `ssh-keygen` | Generates a key pair on your local machine. |
| 2 | `ssh-copy-id username@server_ip` | Copies your public key to the server. |
| 3 | `ssh username@server_ip` | Logs in without typing a password. |

---

## 5. Common options

| Option | Purpose | Example |
|--------|---------|---------|
| `-p` | Connect to a custom SSH port | `ssh -p 2222 user@host` |
| `-v` | Detailed debugging output | `ssh -v user@host` |
| `-C` | Enable compression | `ssh -C user@host` |
| `-4` | Force IPv4 | `ssh -4 user@host` |
| `-6` | Force IPv6 | `ssh -6 user@host` |
| `-X` | Forward GUI applications | `ssh -X user@host` |

---

## 6. Requirements

- The server is on and connected to a network
- Valid login credentials
- OpenSSH server installed and running
- Port 22 (or your custom port) open in the firewall

---

## 7. How SSH secures communication

| Layer | Role |
|-------|------|
| Symmetric encryption | One shared key encrypts and decrypts the session |
| Asymmetric encryption | Public/private key pair for authentication and key exchange |
| Hashing | Ensures message integrity; any tampering is detected |

---

## 8. Troubleshooting

| Error | Cause | Solution |
|-------|-------|----------|
| Connection refused | SSH server not running | Start the `sshd` service |
| Permission denied | Wrong username, password or key | Verify credentials / authorized keys |
| Connection timed out | Server unreachable or firewall blocking | Check network and firewall rules |
| Host key verification failed | Server fingerprint changed | `ssh-keygen -R hostname`, then reconnect |

---

## 9. Security best practices

- Use key authentication instead of passwords
- Disable root login when possible
- Use strong passphrases for private keys
- Change the default SSH port if appropriate
- Keep OpenSSH updated
