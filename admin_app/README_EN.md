# AIFX Admin Desktop App

Python desktop management application for managing the AIFX trading system.

## Two Versions

| File | Connection Type | Description |
|------|----------|------|
| `aifx_admin.py` | HTTP REST API | Simple version, requires API URL |
| `aifx_admin_ws.py` | **WebSocket** | Recommended, real-time connection, more stable |

## Installation

### Windows
```bash
pip install requests python-socketio[client]
```

### macOS / Linux
```bash
pip3 install requests python-socketio[client]
```

## Execution

### WebSocket Version (Recommended)
```bash
python aifx_admin_ws.py
```

### REST API Version
```bash
python aifx_admin.py
```

## Usage

1. Enter server address (Cloudflare Tunnel URL)
2. Enter username: `admin`
3. Enter password: `00000000`
4. Click "Connect and Login"

## Features

- 📊 **Dashboard**: View system status and statistics
- 👥 **User Management**: View user list, enable/disable users
- 📈 **Signal Management**: View trading signal records
- 🤖 **ML Model**: View model status

## WebSocket Version Advantages

- Real-time connection, no need to establish new connection for every request
- Lower latency
- Automatic connection state handling
- Better error handling

## Notes

- Internet connection required
- Cloudflare Quick Tunnel URL changes, please ensure using the latest URL
- Tkinter is built-in with Python, no extra installation needed
