# DockerDiscordControl for Linux 🐧

Control your Docker containers directly from Discord on Linux! This Linux-native version provides a Discord bot and web interface specifically built for **Linux servers** with **multi-architecture support** and **production-ready optimizations**.

[![Version](https://img.shields.io/badge/version-1.0.0--linux-blue.svg)](https://github.com/DockerDiscordControl/DockerDiscordControl-Linux)
[![License](https://img.shields.io/badge/license-MIT-green.svg)](https://github.com/DockerDiscordControl/DockerDiscordControl-Linux/blob/main/LICENSE)
[![Linux Optimized](https://img.shields.io/badge/Linux-Server_Ready-red.svg)](#performance-metrics)
[![Multi-Architecture](https://img.shields.io/badge/Arch-Intel_AMD_ARM64-orange.svg)](#installation)
[![Memory Optimized](https://img.shields.io/badge/RAM-~104MB-green.svg)](#performance-metrics)

## ✨ Features

- **Discord Bot**: Full slash command interface for container management
- **Web Interface**: Secure configuration panel with real-time monitoring
- **Container Control**: Start, stop, restart any Docker container from Discord  
- **Real-time Status**: Live container statistics and health monitoring
- **Scheduled Tasks**: Automated container actions (daily, weekly, monthly)
- **Multi-Language Support**: English, German, French
- **Security**: Channel-based permissions and rate limiting
- **Production Ready**: Optimized for Linux server environments

## 🐧 Linux-Native Features

#### **Multi-Architecture Support**
- **AMD64**: Full support for Intel/AMD x64 processors
- **ARM64**: Native support for ARM-based servers (Raspberry Pi, AWS Graviton, etc.)
- **Cross-Platform Build**: Automatic architecture detection and optimization
- **Native Performance**: No emulation layers required

#### **Linux Server Optimizations**
- **Server Performance**: Higher CPU (2.0 cores) and memory (512MB) limits
- **Resource Scaling**: Auto-scaling with CPU core count
- **Security Hardened**: Non-root user execution, security options, permissions management
- **Health Monitoring**: Built-in health checks and graceful shutdowns
- **Network Isolation**: Dedicated Docker network for security

## 🚀 Performance Metrics

- **Memory Usage**: ~104MB typical usage (tested and verified)
- **CPU Usage**: <3% on 4-core server during normal operation  
- **Container Startup**: ~15-25 seconds on modern Linux servers
- **Build Time**: ~3-5 minutes on typical VPS/cloud instance
- **Concurrent Connections**: Up to 1000 connections per worker

## 🛠️ Quick Installation

### **1. Clone Repository**
git clone https://github.com/DockerDiscordControl/DockerDiscordControl-Linux.git
cd DockerDiscordControl-Linux

### **2. Environment Setup**
cp env.template .env
echo "FLASK_SECRET_KEY=$(openssl rand -hex 32)" >> .env
nano .env  # Add DISCORD_BOT_TOKEN and DISCORD_GUILD_ID

### **3. Start DDC-Linux**
./test-linux-setup.sh  # Validate setup (optional)
docker compose up --build -d

### **4. Access Web Interface**
- **URL**: http://localhost:8374
- **Default Login**: Username admin, Password admin
- **⚠️ CHANGE PASSWORD IMMEDIATELY!**

## 📊 Production Deployment

Perfect for:
- **VPS/Cloud Servers** (AWS, DigitalOcean, Linode, etc.)
- **Raspberry Pi** (ARM64 native support)
- **Container Orchestration** (Docker Swarm, Kubernetes)
- **Enterprise Environments** (Multi-user, security-hardened)

## 🔐 Security Features

- **Non-root Execution**: Container runs as UID/GID 1000
- **Security Hardening**: no-new-privileges and container isolation
- **Docker Socket Security**: Read-only access to Docker socket
- **Network Isolation**: Dedicated ddc-linux-network
- **Authentication**: Web interface requires login
- **Channel Permissions**: Fine-grained Discord access control

## 📚 Documentation

- **README.md**: This comprehensive guide
- **INSTALL_LINUX.md**: Detailed installation instructions
- **QUICK_START.md**: Fast deployment guide
- **TROUBLESHOOTING.md**: Common problem solutions
- **SECURITY.md**: Security best practices

## 🤝 Contributing

Contributions welcome! This Linux version focuses on:
- **Server Performance**: Optimizations for production workloads
- **Security**: Enterprise-grade security features
- **Multi-Architecture**: Intel/AMD and ARM64 support
- **Monitoring**: Health checks and observability

## 📞 Support

- **GitHub Issues**: [Report problems](https://github.com/DockerDiscordControl/DockerDiscordControl-Linux/issues)
- **Discussions**: [Community help](https://github.com/DockerDiscordControl/DockerDiscordControl-Linux/discussions)
- **Wiki**: [Detailed guides](https://github.com/DockerDiscordControl/DockerDiscordControl-Linux/wiki)

---

**Built with ❤️ for Linux system administrators** ��🐳

**Perfect for production Linux servers, VPS, cloud instances, and container orchestration!**
