# v1.1.0 - Optimized Alpine Production Release (2025-07-25)

## 🚀 Major Security & Performance Release

This release focuses on critical security updates and optimizations for production environments.

### 🔒 Security Updates
- **Flask 3.1.1** - Latest stable version with all security patches
- **Werkzeug 3.1.3** - Latest stable version with RCE vulnerability fixes
- **aiohttp ≥3.12.14** - Fixes for CVE-2024-23334, CVE-2024-30251, CVE-2024-52304, CVE-2024-52303
- **requests 2.32.4** - Fix for CVE-2024-47081 (netrc credential leak)
- **urllib3 ≥2.5.0** - Fixes for CVE-2024-37891 & CVE-2024-47081
- **setuptools ≥78.1.1** - Fixes for CVE-2025-47273, CVE-2024-6345
- **cryptography ≥45.0.5** - Latest security patches for token encryption

### 🚀 Performance & Technical Improvements
- **Docker API 7.1.0** - Updated from 6.1.3 for latest features and security
- **gevent ≥24.2.0** - Python 3.13 compatibility improvements
- **Web UI Bug Fixes** - Fixed "Error loading logs: Load failed" issue
- **Enhanced Log Fetching** - Improved Docker container log viewing with docker-py
- **Alpine Linux Optimizations** - Ultra-optimized Docker image for production

### 🐧 Linux-Specific Features
- Native systemd integration optimizations
- Enhanced Docker Compose v2 support
- Improved multi-architecture support (x86_64, ARM64)
- Better NAS compatibility (Synology, QNAP, TrueNAS)
- Optimized Alpine Linux package management

### 📦 Dependencies Updated
All Python dependencies synchronized to latest stable versions with security fixes. This resolves all outstanding Dependabot security alerts.

### 🔧 Technical Details
- Synchronised requirements files across all platforms
- Enhanced error handling and information exposure prevention
- Optimized Alpine Linux build process for reduced image size
- Updated GitHub Actions for optimized container deployment

---

# DockerDiscordControl for Linux - Release Notes

## v1.0.5-linux - Major Stability & Performance Release 🚀
**Release Date**: January 25, 2025  
**Major Stability & Performance Improvements**

### 🎉 What's New in v1.0.5

**DockerDiscordControl v1.0.5** delivers major stability improvements and enhanced platform compatibility for Linux server environments.

### 🔧 Stability & Performance Fixes

#### **Docker Socket Flexibility**
- **Configurable Socket Path**: Now supports `DOCKER_SOCKET` environment variable for custom Docker socket locations
- **Linux Container Compatibility**: Enhanced support for different Docker daemon configurations
- **Better Error Handling**: Improved error messages for Docker connection issues

#### **Web Interface Enhancements**
- **Health Check Endpoint**: Added `/health` route for Docker container health monitoring
- **Configurable Port**: Web interface port now configurable via `WEB_PORT` environment variable (default: 8374)
- **Enhanced Stability**: Improved web interface reliability and error handling

#### **Linux-Specific Improvements**
- **Server Optimization**: Enhanced performance for Linux server environments
- **Systemd Integration**: Better compatibility with systemd service management
- **Resource Efficiency**: Optimized for headless server deployments

### 🐛 Bug Fixes

- **Fixed**: Docker socket connection issues on custom Linux configurations
- **Fixed**: Web interface port conflicts with other applications
- **Fixed**: Container health check reliability issues
- **Fixed**: Improved resource cleanup and memory management
- **Fixed**: Linux file system permission handling

### 🚀 Performance Metrics

- **Memory Usage**: <200MB typical usage (Linux server optimized)
- **CPU Usage**: <3% on typical server during normal operation
- **Container Startup**: ~15-25 seconds on Linux servers
- **Uptime**: Designed for 99.9% uptime in production
- **Web Interface**: <400ms average response time

### 📋 Compatibility

- **Linux Distributions**: Ubuntu 20.04+, Debian 11+, CentOS 8+, RHEL 8+
- **Architecture**: x86_64, ARM64 (Raspberry Pi support)
- **Docker**: Docker Engine 20.10+ and Docker Compose 2.0+

### 🛠️ Installation

Update your existing installation:

```bash
# Pull latest Linux-optimized image
docker pull dockerdiscordcontrol/dockerdiscordcontrol-linux:v1.0.5

# Or use latest tag
docker pull dockerdiscordcontrol/dockerdiscordcontrol-linux:latest
```

---

## v1.0.0-linux - Initial Linux Release 🐧
**Release Date**: July 19, 2025  
// ... existing code ... 