# Firewall Checker Binaries

Download links:
- [Windows](https://raw.githubusercontent.com/xizhendu/public-releases/main/firewallcheck/firewall-checker-windows.exe)
- [Linux](https://raw.githubusercontent.com/xizhendu/public-releases/main/firewallcheck/firewall-checker-linux)
- [README](https://raw.githubusercontent.com/xizhendu/public-releases/main/firewallcheck/README.md)

## Quick Download
```bash
# Windows (PowerShell)
Invoke-WebRequest -Uri https://raw.githubusercontent.com/xizhendu/public-releases/main/firewallcheck/firewall-checker-windows.exe -OutFile firewall-checker-windows.exe

# Linux
wget https://raw.githubusercontent.com/xizhendu/public-releases/main/firewallcheck/firewall-checker-linux
chmod +x firewall-checker-linux
```

## Usage
```bash
# Server mode
firewall-checker-windows.exe -s
firewall-checker-linux -s

# Client mode
firewall-checker-windows.exe -c 192.168.1.100
firewall-checker-linux -c 192.168.1.100
```
