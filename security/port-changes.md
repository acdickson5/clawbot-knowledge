# Port Change Procedures

## SSH Port Change (macOS)

### Step 1: Edit SSH Config
```bash
sudo nano /etc/ssh/sshd_config
```

### Step 2: Find and Change Port
```
# Change this:
#Port 22

# To this (pick a number 1024-65535):
Port 4922
```

### Step 3: Save and Exit
- Ctrl+O to save
- Ctrl+X to exit

### Step 4: Restart SSH
```bash
# On macOS:
sudo launchctl unload /System/Library/LaunchDaemons/ssh.plist
sudo launchctl load /System/Library/LaunchDaemons/ssh.plist
```

### Step 5: Test New Port
```bash
ssh -p 4922 username@localhost
```

### Step 6: Document It
- Write down the new port
- Update any connection scripts

---

## OpenClaw Agent Port Change

### Find Current Config
Look for:
- `config.yaml` or `config.json`
- Environment variables
- Docker port mappings

### Change Port
Edit config file, change port number, restart service.

### Test
Connect to new port to verify.

---

## Common Port Ranges

| Range | Use Case |
|-------|----------|
| 1024-49151 | Registered ports (avoid if possible) |
| 49152-65535 | Dynamic/private ports (good choice) |

### Suggested Ports
- SSH: 4922, 8022, 22222
- HTTP: 8080, 8888, 8008
- HTTPS: 8443, 4443

---

## Verification Commands

```bash
# Check what's listening
sudo lsof -i -P | grep LISTEN

# Check specific port
sudo lsof -i :4922

# Test connection
nc -zv localhost 4922
```
