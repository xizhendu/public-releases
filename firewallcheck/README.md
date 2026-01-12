# WebRTC Firewall Connectivity Checker

Lightweight tool to test UDP port connectivity between nodes for WebRTC deployment.

**Tests 50 ports** across WebRTC range (49152-65535) with automatic synchronization and detailed reporting.

## Quick Start

### 1. Download & Extract
```bash
wget https://github.com/xizhendu/firewallcheck/releases/latest/download/firewall-checker.zip
unzip firewall-checker.zip
cd firewall-checker
```

### 2. Run Server
```bash
# Windows
firewall-checker-windows.exe -s

# Linux
./firewall-checker-linux -s
```

### 3. Run Client (from another machine)
```bash
# Windows
firewall-checker-windows.exe -c 192.168.1.100

# Linux
./firewall-checker-linux -c 192.168.1.100
```

## Command-Line Options

```bash
# Basic usage
-s, --server          Run in server mode
-c, --client IP       Run in client mode (test to IP)

# Advanced options
--ports PORT [...]    Custom ports (default: auto-select 50 ports)
--timeout SEC         Timeout per port (default: 3 seconds)
--output FILE         Save JSON results (default: test_results.json)
--verbose             Show MD5 debug info
-h, --help            Show help
```

## Examples

```bash
# Server with custom ports
firewall-checker-linux -s --ports 50000 51000 52000

# Client with verbose output
firewall-checker-windows.exe -c 192.168.1.100 --verbose

# Client with custom timeout and save results
firewall-checker-linux -c 192.168.1.100 --timeout 5 --output my-test.json
```


## Output

### Client Output
```
============================================================
WebRTC Connectivity Test Results
============================================================
Port       Status          Message                            
------------------------------------------------------------
49606      ✓ SUCCESS       Success                            
50065      ✓ SUCCESS       Success                            
...
------------------------------------------------------------

Summary: 50/50 ports reachable (100.0%)
============================================================

WebRTC Deployment Recommendation:
------------------------------------------------------------
✓ EXCELLENT - Network is highly suitable for WebRTC
  P2P connections should work reliably.
============================================================
```

### Server Logs
```
[16:27:45] Sent port list to 192.168.31.31:45123
[16:27:45] Port 50000: 192.168.31.31:45124 req=47c46c9e... resp=2c6c88cf...
[16:27:45] Port 50001: 192.168.31.31:45125 req=a1b2c3d4... resp=e5f67890...
```

## Configuration

Edit the configuration section at the top of `checker.py` to customize:
- `TEST_PORTS_COUNT`: Number of ports to test (default: 50)
- `TIMEOUT_SECONDS`: Timeout per port test (default: 3)
- `MAX_WORKERS`: Concurrent test threads (default: 5)
- `CONTROL_PORT`: TCP control port (default: 9999)
- `THRESHOLD_*`: Success rate thresholds for recommendations

## System Requirements

### Pre-built Binaries (Recommended)
- **Windows**: Windows 7 or later (64-bit)
- **Linux**: Ubuntu 20.04+ / RHEL 8+ / any modern x86_64 Linux with GLIBC 2.31+
- **No Python or dependencies required**

### Python Script (Advanced)
- Python 3.6+
- Standard library only (no external dependencies)

## Package Contents

```
firewall-checker/
├── firewall-checker-windows.exe   # Windows binary
├── firewall-checker-linux          # Linux binary
└── README.md                       # This file
```

**Source**: `checker.py` (Python script, optional)

## License

MIT
