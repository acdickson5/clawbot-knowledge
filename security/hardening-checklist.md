# Security Hardening Checklist

## Immediate Priority

### 1. Change Default Ports
See [port-changes.md](port-changes.md) for detailed steps.

### 2. Enable Firewall (macOS)
```bash
# Check status
sudo /usr/libexec/ApplicationFirewall/socketfilterfw --getglobalstate

# Enable
sudo /usr/libexec/ApplicationFirewall/socketfilterfw --setglobalstate on
```

GUI method:
- System Preferences → Security & Privacy → Firewall → Turn On

### 3. Disable Password Login (SSH Keys Only)
Edit `/etc/ssh/sshd_config`:
```
PasswordAuthentication no
PubkeyAuthentication yes
ChallengeResponseAuthentication no
```

### 4. Check Running Services
```bash
# See what's listening on ports
sudo lsof -i -P | grep LISTEN

# Disable unnecessary services
```

### 5. Enable Auto-Updates
- macOS: System Preferences → Software Update → Automatic Updates

## Medium Priority

### 6. Install Fail2Ban
```bash
brew install fail2ban
# Configure to block IPs after failed login attempts
```

### 7. Review File Permissions
```bash
# Check sensitive files
ls -la ~/.ssh/
chmod 700 ~/.ssh
chmod 600 ~/.ssh/*
```

### 8. Disable Root Login
In `/etc/ssh/sshd_config`:
```
PermitRootLogin no
```

## Low Priority

### 9. VPN-Only Access
- Disable external SSH entirely
- Use Tailscale/WireGuard for remote access

### 10. Two-Factor Authentication
- For SSH: Google Authenticator PAM module
- For web interfaces: Enable 2FA

---

## Documentation Checklist

- [ ] All port changes documented
- [ ] SSH keys backed up to password manager
- [ ] List of running services and ports
- [ ] Firewall rules documented
- [ ] Backup procedure in place

---

## Quick Reference

| Task | Command |
|------|---------|
| Check open ports | `sudo lsof -i -P \| grep LISTEN` |
| Check firewall | `sudo /usr/libexec/ApplicationFirewall/socketfilterfw --getglobalstate` |
| Test SSH port | `ssh -p PORT user@host` |
| View auth log | `tail -f /var/log/auth.log` |

---

*Last updated: 2026-03-07*
