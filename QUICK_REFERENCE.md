# Terminal UI - Quick Reference Guide

## 📋 Module Overview

| Module | Key Features | Priority |
|--------|--------------|----------|
| 📊 **Dashboard** | System overview, quick status, navigation | Phase 1 |
| 💾 **Storage Management** | Disk usage, directory analysis, I/O metrics, SMART health | Phase 1 |
| 📈 **Task Monitors** | CPU/Memory graphs, process explorer, load averages | Phase 1 |
| 🌐 **Network Management** | Interface status, traffic monitor, connections, tools | Phase 1 |
| 🔄 **Process Management** | Process control, service manager, detailed info | Phase 2 |
| 📝 **Log Viewer** | System/app logs, real-time streaming, filtering | Phase 2 |
| 👥 **User Management** | Active users, sessions, user operations | Phase 3 |
| 🐳 **Container Management** | Docker containers, images, stats | Phase 3 |
| 📅 **Scheduled Tasks** | Cron jobs, task scheduler, at jobs | Phase 3 |
| 🔐 **Security & Permissions** | File permissions, security logs, SSH management | Phase 3 |
| 🔧 **System Information** | Hardware/software info, sensors, BIOS details | Phase 2 |
| 📦 **Package Manager** | Installed packages, updates, operations | Phase 3 |
| ⚡ **Performance Metrics** | Performance monitoring, benchmarking, alerts | Phase 4 |
| 🔄 **Backup & Recovery** | Backup status, operations, snapshots | Phase 4 |
| ⚙️ **Settings** | Appearance, intervals, alerts, shortcuts | Phase 2 |
| 🆘 **Help** | Quick help, tutorials, documentation | Phase 2 |

## 🎯 MVP Features (Phase 1)

### Storage Management Must-Haves:
- ✅ Visual disk usage bars with color coding
- ✅ Mount points list
- ✅ Directory size tree (sortable)
- ✅ Real-time I/O statistics

### Task Monitors Must-Haves:
- ✅ CPU usage per core with graphs
- ✅ Memory usage visualization
- ✅ Top processes list (sortable by CPU/Memory)
- ✅ Load averages display

### Network Management Must-Haves:
- ✅ Interface list with IP addresses
- ✅ Real-time bandwidth graphs
- ✅ Active connections table

### Dashboard Must-Haves:
- ✅ System health summary
- ✅ Quick access navigation
- ✅ Recent alerts
- ✅ Uptime display

## ⌨️ Keyboard Shortcuts

### Global:
- `Ctrl+Q` - Quit application
- `Ctrl+H` - Go to Dashboard
- `/` - Search
- `Esc` - Back/Cancel
- `F1` - Help
- `Tab` - Next section
- `Shift+Tab` - Previous section

### Module Navigation:
- `Ctrl+D` - Dashboard
- `Ctrl+S` - Storage Management
- `Ctrl+T` - Task Monitors
- `Ctrl+N` - Network Management
- `Ctrl+P` - Process Management
- `Ctrl+L` - Log Viewer
- `Ctrl+,` - Settings

## 🎨 Visual Design Elements

### Color Scheme:
- 🟢 **Green**: Healthy, Normal (0-70% usage)
- 🟡 **Yellow**: Warning (70-90% usage)
- 🔴 **Red**: Critical (90-100% usage)
- 🔵 **Blue**: Information, Neutral
- ⚪ **White/Gray**: Text, Borders

### UI Components:
- Bar charts for storage/usage
- Line graphs for time-series data
- Tables with sortable columns
- Progress bars with percentages
- Status indicators with icons
- Scrollable panels with borders

## 💡 Implementation Tips

### Data Collection:
```bash
# Storage
df -h                    # Disk space
du -sh /path/*          # Directory sizes
iostat                  # I/O stats
smartctl -a /dev/sda    # SMART data

# Processes
ps aux                  # Process list
top -bn1                # CPU/Memory snapshot
uptime                  # Load averages

# Network
ip addr                 # Interface info
ifstat                  # Bandwidth stats
ss -tunapl             # Connections
```

### Recommended Libraries:
- **Rust**: `tui-rs`, `crossterm`, `sysinfo`
- **Python**: `textual`, `rich`, `psutil`
- **Go**: `bubbletea`, `termui`, `gopsutil`
- **Node.js**: `blessed`, `blessed-contrib`, `systeminformation`

## 📊 Data Refresh Rates

| Module | Default Interval | Configurable Range |
|--------|------------------|-------------------|
| CPU/Memory | 1 second | 0.5 - 5 seconds |
| Disk I/O | 1 second | 1 - 10 seconds |
| Network | 1 second | 0.5 - 5 seconds |
| Processes | 2 seconds | 1 - 10 seconds |
| Storage Space | 5 seconds | 5 - 60 seconds |
| Logs | Real-time | N/A |

## 🔒 Permission Requirements

| Feature | Permission Level | Notes |
|---------|-----------------|-------|
| View metrics | User | Read-only access |
| Kill processes | User (own) / Root (all) | Requires ownership or sudo |
| Mount/Unmount | Root | System modification |
| Service control | Root | Systemd operations |
| User management | Root | Security critical |
| Package operations | Root | System modification |

## 📁 Configuration File Structure

```yaml
# ~/.config/ramsays-tui/config.yaml

appearance:
  theme: "dark"  # dark, light, custom
  color_scheme: "default"
  font_size: "medium"

refresh_intervals:
  cpu_memory: 1
  network: 1
  storage: 5
  processes: 2

alerts:
  cpu_threshold: 90
  memory_threshold: 85
  disk_threshold: 90
  enable_notifications: true
  enable_sounds: false

modules:
  enabled:
    - dashboard
    - storage
    - tasks
    - network
    - processes
  disabled:
    - containers  # Docker not installed

shortcuts:
  quit: "Ctrl+Q"
  dashboard: "Ctrl+H"
  storage: "Ctrl+S"
  # ... custom bindings
```

## 🚀 Getting Started Checklist

- [ ] Choose technology stack (Rust/Python/Go/Node.js)
- [ ] Set up project structure
- [ ] Implement Dashboard (MVP)
- [ ] Implement Storage Management
- [ ] Implement Task Monitors
- [ ] Implement Network Management
- [ ] Add keyboard navigation
- [ ] Add color scheme
- [ ] Implement settings/config
- [ ] Add help system
- [ ] Test on Linux
- [ ] Test on macOS
- [ ] Package and distribute

## 📚 Resources

### Terminal UI Frameworks:
- **Rust**: https://github.com/fdehau/tui-rs
- **Python**: https://github.com/Textualize/textual
- **Go**: https://github.com/charmbracelet/bubbletea
- **Node.js**: https://github.com/chjj/blessed

### System Monitoring:
- psutil documentation: https://psutil.readthedocs.io/
- /proc filesystem: https://www.kernel.org/doc/Documentation/filesystems/proc.txt
- Linux Performance: https://www.brendangregg.com/linuxperf.html

---

For complete details, see [TERMINAL_UI_OUTLINE.md](TERMINAL_UI_OUTLINE.md)
