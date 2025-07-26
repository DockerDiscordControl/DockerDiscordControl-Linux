# DockerDiscordControl for Linux 🐧

Control your Docker containers directly from Discord on Linux! This Linux-native version provides a Discord bot and web interface specifically optimized for **Linux server environments** with **Docker Engine integration** and **multi-architecture support**.

---

## 💖 **Support DDC Development**

**Help keep DockerDiscordControl growing and improving across all platforms!**

<div align="center">

[![Buy Me A Coffee](https://img.shields.io/badge/☕_Buy_Me_A_Coffee-Support_DDC-orange?style=for-the-badge&logo=buy-me-a-coffee&logoColor=white)](https://buymeacoffee.com/dockerdiscordcontrol)
&nbsp;&nbsp;&nbsp;
[![PayPal Donation](https://img.shields.io/badge/💝_PayPal_Donation-Support_DDC-blue?style=for-the-badge&logo=paypal&logoColor=white)](https://paypal.me/dockerdiscordcontrol)

**Your support helps maintain DDC across Windows, Linux, macOS, and Universal versions!**

</div>

---

**Homepage:** [DDC for Linux](https://github.com/DockerDiscordControl/DockerDiscordControl-Linux) | **Main Project:** [DockerDiscordControl](https://github.com/DockerDiscordControl/DockerDiscordControl)

[![Version](https://img.shields.io/badge/version-v1.1.2-blue.svg)](https://github.com/DockerDiscordControl/DockerDiscordControl-Linux/releases/latest)
[![License](https://img.shields.io/badge/license-MIT-green.svg)](https://github.com/DockerDiscordControl/DockerDiscordControl-Linux/blob/main/LICENSE)
[![Linux Optimized](https://img.shields.io/badge/Linux-Docker_Engine-blue.svg)](#performance-metrics)
[![Multi-Architecture](https://img.shields.io/badge/Arch-x86_64_ARM64-orange.svg)](#installation)
[![Memory Optimized](https://img.shields.io/badge/RAM-~95MB-green.svg)](#performance-metrics)

## 🚀 Revolutionary Linux Performance

**Major Linux-Specific Optimizations Delivered:**

- **Docker Engine Integration**: Native Linux Docker Engine support with 95MB typical RAM usage
- **Multi-Distribution Support**: Compatible with Ubuntu, Debian, CentOS, RHEL, and other major distributions
- **ARM64 & x86_64**: Full architecture support including Raspberry Pi and ARM servers
- **Systemd Integration**: Native service management and auto-start capabilities
- **Alpine Optimization**: Ultra-lightweight Alpine Linux base for maximum server efficiency

## 🐳 Docker Hub Repository

**Linux-Optimized Image:** \`dockerdiscordcontrol/dockerdiscordcontrol-linux\`

This repository publishes **only** the Linux-optimized Alpine-based image, specifically tuned for:
- x86_64 and ARM64 architecture compatibility
- Linux Docker Engine integration
- Optimal resource usage on Linux servers
- Native Linux Docker socket handling

**Other Platform Images:**
- **Universal/Unraid**: \`dockerdiscordcontrol/dockerdiscordcontrol\`
- **Windows**: \`dockerdiscordcontrol/dockerdiscordcontrol-windows\`  
- **macOS**: \`dockerdiscordcontrol/dockerdiscordcontrol-mac\`

## 🛠️ Quick Installation

### **Docker Hub Installation (Recommended)**
\`\`\`bash
# Pull the Linux-optimized image
docker pull dockerdiscordcontrol/dockerdiscordcontrol-linux:latest

# Run with docker compose
docker compose up -d

# Or run directly
docker run -d --name ddc \\
  -p 8374:8374 \\
  -v /var/run/docker.sock:/var/run/docker.sock \\
  -v ./config:/app/config \\
  -v ./logs:/app/logs \\
  dockerdiscordcontrol/dockerdiscordcontrol-linux:latest
\`\`\`

## 🔧 Configuration

1. **Access the Web Interface**: \`http://your-server-ip:8374\`
2. **Default Login**: \`admin\` / \`admin\` (change immediately!)
3. **Configure Discord Bot**: Add your bot token and guild ID
4. **Set Docker Settings**: Configure container refresh intervals
5. **Channel Permissions**: Set up Discord channel access controls

## 🆕 Latest Updates (v1.1.2)

### **✅ Critical ConfigManager Stability Fixes**
- **Fixed ConfigManager**: Resolved missing attributes and cache invalidation issues
- **Eliminated CPU spikes**: Fixed restart loops that caused high CPU usage
- **Enhanced error handling**: Improved subscriber notification system
- **System stability**: Eliminated config cache reload loops

### **✅ Linux Server Optimizations**
- **Multi-distribution support**: Tested on Ubuntu, Debian, CentOS, RHEL, Fedora
- **Resource optimization**: ~95MB RAM usage with minimal CPU impact
- **Health monitoring**: Added \`/health\` endpoint for proper Docker health checks  
- **Alpine efficiency**: Ultra-lightweight Alpine Linux base for maximum server performance

**🎉 Ready for production deployment on any Linux Docker Engine environment!**

---

## 🌟 **Show Your Support**

If DockerDiscordControl helps you manage your Linux containers, please consider supporting the project:

<div align="center">

### **💖 Support DDC Development**

[![⭐ Star on GitHub](https://img.shields.io/badge/⭐_Star_on_GitHub-Show_Support-brightgreen?style=for-the-badge&logo=github)](https://github.com/DockerDiscordControl/DockerDiscordControl-Linux)

[![☕ Buy Me A Coffee](https://img.shields.io/badge/☕_Buy_Me_A_Coffee-orange?style=for-the-badge&logo=buy-me-a-coffee&logoColor=white)](https://buymeacoffee.com/dockerdiscordcontrol)
&nbsp;&nbsp;
[![💝 PayPal Donation](https://img.shields.io/badge/💝_PayPal_Donation-blue?style=for-the-badge&logo=paypal&logoColor=white)](https://paypal.me/dockerdiscordcontrol)

**Your support helps maintain DDC across all platforms and develop new features!**

</div>

---

**🐧 Built with ❤️ for Linux server environments**

**🚀 Perfect for Linux servers, home labs, and production environments!** 

**⭐ Star this repo if DockerDiscordControl helps you manage your Linux containers!**
