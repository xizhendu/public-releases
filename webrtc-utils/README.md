# CheckNAT - WebRTC NAT Type Checker

Download links:
- [Linux](https://raw.githubusercontent.com/xizhendu/public-releases/main/webrtc-utils/checknat-linux)
- [Windows](https://raw.githubusercontent.com/xizhendu/public-releases/main/webrtc-utils/checknat-windows.exe)
- [macOS](https://raw.githubusercontent.com/xizhendu/public-releases/main/webrtc-utils/checknat-macos)

## Quick Download
```bash
# Linux
wget https://raw.githubusercontent.com/xizhendu/public-releases/main/webrtc-utils/checknat-linux
chmod +x checknat-linux

# macOS
wget https://raw.githubusercontent.com/xizhendu/public-releases/main/webrtc-utils/checknat-macos
chmod +x checknat-macos

# Windows (PowerShell)
Invoke-WebRequest -Uri https://raw.githubusercontent.com/xizhendu/public-releases/main/webrtc-utils/checknat-windows.exe -OutFile checknat-windows.exe
```

## Usage
```bash
# Check NAT type
./checknat-linux
./checknat-macos
checknat-windows.exe

# Use custom STUN server
./checknat-linux --stun stun.l.google.com:19302
```

See the main repo for full documentation: https://github.com/xizhendu/webrtc-utils
