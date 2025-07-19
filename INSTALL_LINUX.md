# DockerDiscordControl Linux - Installation Guide

Complete installation guide for DockerDiscordControl on Linux systems.

## 🎯 Quick Install

git clone https://github.com/DockerDiscordControl/DockerDiscordControl-Linux.git
cd DockerDiscordControl-Linux
cp env.template .env
echo "FLASK_SECRET_KEY=$(openssl rand -hex 32)" >> .env
nano .env  # Add DISCORD_BOT_TOKEN and DISCORD_GUILD_ID
docker compose up --build -d
# Access: http://localhost:8374

## 📋 Prerequisites

### System Requirements
- **Linux Distribution**: Ubuntu 20.04+, Debian 11+, CentOS 8+, or any modern Linux
- **Architecture**: AMD64 (x86_64) or ARM64 (aarch64) 
- **RAM**: 2GB minimum (4GB+ recommended)
- **Storage**: 2GB free space
- **Network**: Internet access for Discord API and Docker Hub

### Required Software
- **Docker**: Version 20.10 or newer
- **Docker Compose**: Version 2.0 or newer
- **Git**: For cloning the repository
- **OpenSSL**: For generating secure keys

## 🐳 Install Docker

### Ubuntu/Debian
curl -fsSL https://get.docker.com -o get-docker.sh
sudo sh get-docker.sh
sudo usermod -aG docker $USER
newgrp docker
sudo systemctl enable docker
sudo systemctl start docker

### CentOS/RHEL/Rocky Linux
curl -fsSL https://get.docker.com -o get-docker.sh
sudo sh get-docker.sh
sudo usermod -aG docker $USER
newgrp docker
sudo systemctl enable docker
sudo systemctl start docker

### Raspberry Pi (ARM64)
sudo apt update && sudo apt upgrade -y
curl -fsSL https://get.docker.com -o get-docker.sh
sudo sh get-docker.sh
sudo usermod -aG docker $USER
newgrp docker

## 🚀 Launch DockerDiscordControl

### Start Services
docker compose up --build -d
sleep 30
docker ps | grep ddc-linux
docker compose logs ddc | tail -20

### Verify Installation
curl http://localhost:8374
# Should return: {"message":"Authentication Required"}
docker stats ddc-linux --no-stream

## 🌐 Web Interface Setup

1. Open browser to **http://localhost:8374**
2. Login: Username `admin`, Password `admin`
3. **⚠️ CHANGE PASSWORD IMMEDIATELY!**
4. Configure Discord bot token and server ID
5. Select container permissions
6. Restart: `docker compose restart ddc`

## 🔧 Production Configuration

### Systemd Service
sudo nano /etc/systemd/system/ddc-linux.service

[Unit]
Description=DockerDiscordControl Linux
After=docker.service
Requires=docker.service

[Service]
Type=oneshot
RemainAfterExit=yes
WorkingDirectory=/opt/DockerDiscordControl-Linux
ExecStart=/usr/bin/docker compose up -d
ExecStop=/usr/bin/docker compose down
TimeoutStartSec=0

[Install]
WantedBy=multi-user.target

sudo systemctl enable ddc-linux
sudo systemctl start ddc-linux

## 🐛 Troubleshooting

### Docker Issues
sudo systemctl start docker
sudo usermod -aG docker $USER && newgrp docker

### Container Issues  
docker compose logs ddc
docker system prune
docker compose up --build -d

### Performance Issues
docker stats ddc-linux
htop
df -h

## 📊 Verification Checklist

- [ ] Docker is installed and running
- [ ] Container ddc-linux is running  
- [ ] Web interface accessible at http://localhost:8374
- [ ] Can login with admin credentials
- [ ] Discord bot token configured
- [ ] Memory usage ~100-150MB
- [ ] CPU usage <5% when idle

---

**Installation complete!** 🎉
