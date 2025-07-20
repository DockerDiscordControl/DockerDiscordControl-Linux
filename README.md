# DockerDiscordControl - Linux Edition

[![Docker Hub](https://img.shields.io/docker/v/dockerdiscordcontrol/dockerdiscordcontrol-linux?label=docker%20hub)](https://hub.docker.com/r/dockerdiscordcontrol/dockerdiscordcontrol-linux)
[![Docker Pulls](https://img.shields.io/docker/pulls/dockerdiscordcontrol/dockerdiscordcontrol-linux)](https://hub.docker.com/r/dockerdiscordcontrol/dockerdiscordcontrol-linux)
[![Image Size](https://img.shields.io/docker/image-size/dockerdiscordcontrol/dockerdiscordcontrol-linux/latest)](https://hub.docker.com/r/dockerdiscordcontrol/dockerdiscordcontrol-linux)

**Control your Docker containers directly from Discord on Linux systems!**

DockerDiscordControl-Linux is optimized for Linux server environments, providing high-performance Docker container management through Discord bot commands with server-grade reliability and security.

**🌐 Homepage: [https://ddc.bot](https://ddc.bot)**

## 🚀 Quick Start

### Using Docker Hub

```bash
# Pull the latest Linux-optimized image
docker pull dockerdiscordcontrol/dockerdiscordcontrol-linux:latest

# Run with Docker Compose
docker-compose up -d
```

### Using Docker Run

```bash
docker run -d \
  --name dockerdiscordcontrol-linux \
  -v /var/run/docker.sock:/var/run/docker.sock:ro \
  -v ./config:/app/config \
  -e DISCORD_BOT_TOKEN=your_bot_token_here \
  -e ALLOWED_CHANNELS=channel_id_1,channel_id_2 \
  -e ALLOWED_ROLES=role_id_1,role_id_2 \
  -p 8080:8080 \
  dockerdiscordcontrol/dockerdiscordcontrol-linux:latest
```

## ✨ Linux-Specific Features

- **High-Performance Server Optimization**: Tuned for Linux server environments
- **Systemd Integration**: Native systemd service management support  
- **Advanced Process Management**: Multi-threaded container operations
- **Memory Optimization**: Efficient memory usage for production workloads
- **Security Hardening**: SELinux/AppArmor compatibility with enhanced security

## 🏗️ Architecture

This Linux-optimized version includes:

- **Alpine Linux Base**: Ultra-lightweight and secure foundation
- **Python 3.13**: Latest Python runtime with Linux optimizations
- **Supervisor**: Advanced process management for server environments
- **Multi-Architecture**: Supports AMD64, ARM64, and ARM7 platforms

## 📋 Requirements

### System Requirements
- **Linux Distribution**: Ubuntu 20.04+, Debian 11+, CentOS 8+, RHEL 8+, or Alpine
- **Docker Engine**: 20.10+ or Docker CE
- **Architecture**: AMD64, ARM64, or ARM7
- **Memory**: Minimum 256MB RAM (512MB+ recommended)
- **Storage**: 200MB+ free disk space

### Discord Requirements
- Discord bot token with necessary permissions
- Guild/server with appropriate permissions
- Channel IDs for command execution

## 🔧 Configuration

### Environment Variables

| Variable | Description | Required | Default |
|----------|-------------|----------|---------|
| `DISCORD_BOT_TOKEN` | Your Discord bot token | ✅ Yes | - |
| `ALLOWED_CHANNELS` | Comma-separated channel IDs | ✅ Yes | - |
| `ALLOWED_ROLES` | Comma-separated role IDs | ✅ Yes | - |
| `LOG_LEVEL` | Logging level (DEBUG, INFO, WARNING, ERROR) | ❌ No | `INFO` |
| `WEB_UI_PORT` | Web interface port | ❌ No | `8080` |
| `MAX_CONTAINERS` | Maximum containers to manage | ❌ No | `100` |
| `WORKER_THREADS` | Number of worker threads | ❌ No | `4` |

### Docker Compose Example

```yaml
version: '3.8'
services:
  dockerdiscordcontrol:
    image: dockerdiscordcontrol/dockerdiscordcontrol-linux:latest
    container_name: dockerdiscordcontrol-linux
    restart: unless-stopped
    volumes:
      - /var/run/docker.sock:/var/run/docker.sock:ro
      - ./config:/app/config
      - ./logs:/app/logs
    environment:
      - DISCORD_BOT_TOKEN=${DISCORD_BOT_TOKEN}
      - ALLOWED_CHANNELS=${ALLOWED_CHANNELS}
      - ALLOWED_ROLES=${ALLOWED_ROLES}
      - LOG_LEVEL=INFO
      - WORKER_THREADS=4
    ports:
      - "8080:8080"
    networks:
      - dockerdiscordcontrol
    labels:
      - "com.dockerdiscordcontrol.version=1.0.3"
      - "com.dockerdiscordcontrol.platform=linux"

networks:
  dockerdiscordcontrol:
    driver: bridge
```

## 🎮 Discord Commands

### Container Management
- `/docker ps` - List running containers
- `/docker start <container>` - Start a container
- `/docker stop <container>` - Stop a container
- `/docker restart <container>` - Restart a container
- `/docker logs <container>` - View container logs
- `/docker stats` - Show container statistics

### System Information
- `/system info` - Display system information
- `/system resources` - Show resource usage
- `/docker version` - Docker version information

### Advanced Commands
- `/compose up <service>` - Start Docker Compose services
- `/compose down` - Stop Docker Compose services
- `/network ls` - List Docker networks
- `/volume ls` - List Docker volumes

## 🌐 Web Interface

Access the web interface at `http://localhost:8080` for:

- **Real-time Container Monitoring**: Live status and metrics
- **Configuration Management**: Easy setup and configuration
- **Log Viewer**: Centralized log management
- **Task Scheduler**: Automated container operations
- **Performance Dashboard**: Resource usage and optimization

## 🔒 Security Features

### Built-in Security
- **Role-based Access Control**: Discord role verification
- **Channel Restrictions**: Limit commands to specific channels
- **Command Auditing**: Full audit trail of all commands
- **Rate Limiting**: Prevention of command spam
- **Input Validation**: Sanitized command parameters

### Linux Security Integration
- **SELinux Compatibility**: Full support for SELinux environments
- **AppArmor Profiles**: Security profiles for Ubuntu/Debian systems
- **User Namespace Support**: Enhanced container isolation
- **Capability Management**: Fine-grained privilege control

## 🔍 Monitoring & Logging

### Log Levels
- **DEBUG**: Detailed debugging information
- **INFO**: General operational messages
- **WARNING**: Warning messages for attention
- **ERROR**: Error conditions

### Health Checks
The container includes built-in health checks:

```bash
# Check container health
docker inspect --format='{{.State.Health.Status}}' dockerdiscordcontrol-linux

# View health check logs
docker inspect dockerdiscordcontrol-linux | grep -A5 Health
```

### Performance Monitoring
```bash
# Monitor resource usage
docker stats dockerdiscordcontrol-linux

# View detailed metrics
curl http://localhost:8080/metrics
```

## 🛠️ Troubleshooting

### Common Issues

#### Bot Not Responding
```bash
# Check bot token and permissions
docker logs dockerdiscordcontrol-linux --tail 50

# Verify Discord connectivity
docker exec dockerdiscordcontrol-linux python -c "import discord; print('Discord.py version:', discord.__version__)"
```

#### Docker Socket Issues
```bash
# Verify Docker socket permissions
ls -la /var/run/docker.sock

# Test Docker connectivity
docker exec dockerdiscordcontrol-linux docker version
```

#### Linux-Specific Issues
- Ensure Docker daemon is running: `systemctl status docker`
- Check firewall settings: `ufw status` or `iptables -L`
- Verify user permissions: `groups $USER`

### Performance Optimization
- Adjust `WORKER_THREADS` based on CPU cores
- Increase `MAX_CONTAINERS` for large deployments
- Use specific tags instead of `latest` for production
- Enable log rotation for long-running deployments

## 📦 Tags & Versions

| Tag | Description | Architecture |
|-----|-------------|--------------|
| `latest` | Latest stable release | `linux/amd64`, `linux/arm64`, `linux/arm/v7` |
| `1.0.3` | Version 1.0.3 | `linux/amd64`, `linux/arm64`, `linux/arm/v7` |
| `alpine` | Alpine Linux base | `linux/amd64`, `linux/arm64`, `linux/arm/v7` |
| `debian` | Debian Slim base | `linux/amd64`, `linux/arm64` |

## 🤝 Support

### Documentation
- **🌐 Official Homepage**: [https://ddc.bot](https://ddc.bot)
- **Main Repository (Unraid)**: [DockerDiscordControl](https://github.com/DockerDiscordControl/DockerDiscordControl)
- **Linux Repository**: [DockerDiscordControl-Linux](https://github.com/DockerDiscordControl/DockerDiscordControl-Linux)
- **Installation Guide**: [Linux Setup Instructions](https://github.com/DockerDiscordControl/DockerDiscordControl/blob/main/INSTALL_LINUX.md)
- **Wiki**: [Comprehensive Documentation](https://github.com/DockerDiscordControl/DockerDiscordControl/wiki)

### Community
- **Discord Server**: Join our community for support
- **GitHub Issues**: Report bugs and feature requests
- **GitHub Discussions**: Community Q&A and discussions

### Professional Support
For enterprise support and custom implementations, please contact our team through GitHub.

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](https://github.com/DockerDiscordControl/DockerDiscordControl/blob/main/LICENSE) file for details.

## 🎉 Contributing

We welcome contributions! Please see our [Contributing Guide](https://github.com/DockerDiscordControl/DockerDiscordControl/blob/main/CONTRIBUTING.md) for details.

## 💝 Support DDC Development

Help keep DockerDiscordControl growing and improving for Linux server environments:

- **[☕ Buy Me A Coffee](https://buymeacoffee.com/dockerdiscordcontrol)** - Quick one-time support for development
- **[💳 PayPal Donation](https://www.paypal.com/donate/?hosted_button_id=DOCKERDISCORDCONTROL)** - Direct contribution to the project  
- **[💖 GitHub Sponsors](https://github.com/sponsors/DockerDiscordControl)** - Ongoing monthly support

**Your support helps:**
- 🛠️ Maintain DDC for Linux with latest Docker Engine compatibility
- ✨ Develop new Linux-specific features and server optimizations  
- 🔒 Keep DockerDiscordControl zero-vulnerability secure for production environments
- 📚 Create comprehensive Linux server documentation and guides
- 🚀 Performance optimizations for high-performance Linux deployments

**Thank you for supporting open source development!** 🙏

---

**Made with ❤️ for the Linux server community**

[![GitHub](https://img.shields.io/badge/GitHub-DockerDiscordControl-blue?logo=github)](https://github.com/DockerDiscordControl)
[![Docker Hub](https://img.shields.io/badge/Docker%20Hub-dockerdiscordcontrol-blue?logo=docker)](https://hub.docker.com/u/dockerdiscordcontrol)
