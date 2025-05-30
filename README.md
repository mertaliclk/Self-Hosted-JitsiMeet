# Video Conferencing System with Jitsi Meet

![Ubuntu](https://img.shields.io/badge/Ubuntu-22.04-orange)
![Jitsi](https://img.shields.io/badge/Jitsi-Meet-blue)
![SSL](https://img.shields.io/badge/SSL-Let's%20Encrypt-green)
![Security](https://img.shields.io/badge/Security-Authentication-lightgrey)
![DigitalOcean](https://img.shields.io/badge/DigitalOcean-Cloud-blue)
![METUnic](https://img.shields.io/badge/METUnic-Domain-orange)

A comprehensive video conferencing solution implementing Jitsi Meet on Ubuntu 22.04, featuring secure authentication, high-quality video streaming, and robust meeting management capabilities. This project is hosted on DigitalOcean and uses METUnic for domain management.

## 📋 Overview

This project implements a self-hosted video conferencing system using Jitsi Meet, providing a secure and reliable platform for online meetings, webinars, and virtual classrooms. The system is deployed on DigitalOcean's cloud infrastructure and uses METUnic for domain management, ensuring high availability and professional domain handling.

## 🎯 Project Goals

- Implement secure Jitsi Meet server on Ubuntu 22.04
- Configure SSL certificates for secure connections
- Set up user authentication system
- Enable meeting recording capabilities
- Ensure robust and reliable operation in production environment
- Implement cloud-based hosting solution
- Establish professional domain management

## 📊 Key Features

### Video Conferencing
- HD video conferencing with up to 100 participants
- Real-time chat functionality
- Screen sharing capabilities
- Meeting recording options
- Customizable meeting rooms
- Mobile device support

### Security Features
- SSL/TLS encryption
- Password-based authentication
- Guest access control
- Meeting password protection
- Rate limiting implementation
- Cloud-based security measures

### Meeting Management
- Meeting scheduling system
- Participant management
- Recording storage
- Chat moderation
- File sharing capabilities
- Cloud-based storage solutions

## 🛠️ Technologies Used

- Ubuntu 22.04 LTS
- Jitsi Meet
- Let's Encrypt SSL
- Prosody XMPP Server
- Nginx Web Server
- PostgreSQL Database
- DigitalOcean Cloud Platform
- METUnic Domain Services

## 📈 Project Structure

1. **Server Setup**
   - Ubuntu 22.04 installation on DigitalOcean
   - System updates and dependencies
   - Network configuration
   - Cloud infrastructure setup

2. **Jitsi Meet Installation**
   - Repository configuration
   - Package installation
   - SSL certificate setup
   - Domain configuration via METUnic

3. **Security Implementation**
   - Authentication system
   - SSL configuration
   - Firewall setup
   - Cloud security measures

4. **Meeting Management**
   - User administration
   - Meeting scheduling
   - Recording management
   - Cloud storage integration

## 💻 Installation

1. Set up DigitalOcean Droplet:
   - Create new Ubuntu 22.04 droplet
   - Configure firewall rules
   - Set up SSH access

2. Configure Domain (METUnic):
   - Set up DNS records
   - Configure domain forwarding
   - Enable SSL certificate

3. Update system packages:
```bash
apt update -y
apt upgrade -y
```

4. Install required dependencies:
```bash
apt install curl gnupg2 wget -y
```

5. Add Jitsi Meet repository:
```bash
curl https://download.jitsi.org/jitsi-key.gpg.key -o jitsi-key.gpg.key
gpg --output /usr/share/keyrings/jitsi-key.gpg --dearmor jitsi-key.gpg.key
```

6. Create Jitsi repository file:
```bash
echo "deb [signed-by=/usr/share/keyrings/jitsi-key.gpg] https://download.jitsi.org stable/" | sudo tee /etc/apt/sources.list.d/jitsi-stable.list
```

7. Install Jitsi Meet:
```bash
apt install jitsi-meet -y
```

8. Configure SSL certificate:
- Choose Let's Encrypt during installation
- Enter your METUnic domain name
- Provide email address for notifications

9. Enable authentication:
```bash
nano /etc/prosody/conf.avail/your-domain.cfg.lua
```
Add authentication configuration:
```lua
authentication = "internal_plain"
```

10. Create admin user:
```bash
prosodyctl register admin your-domain.com yourpassword
```

11. Restart services:
```bash
systemctl restart prosody.service jicofo.service jitsi-videobridge2.service
```

## 🔍 Key Findings

- Successful implementation of secure video conferencing system
- Effective user authentication and access control
- High-quality video streaming capabilities
- Robust meeting management features
- Comprehensive security measures
- Efficient cloud-based hosting solution
- Professional domain management

## 📊 System Requirements

- Ubuntu 22.04 LTS
- Minimum 4GB RAM
- 2 CPU cores
- 20GB storage space
- Valid domain name (METUnic)
- Static IP address
- DigitalOcean account
- SSL certificate

## 👤 Author

Mert Ali Celik

## 🙏 Acknowledgments

- [Jitsi Meet](https://github.com/jitsi/jitsi-meet) development team
- [DigitalOcean](https://www.digitalocean.com/) for cloud hosting
- [METUnic](https://app.metunic.com.tr/client/login/) for domain services
- Ubuntu community
- Let's Encrypt for SSL certificates
- Open-source community

## 📚 Documentation

For detailed documentation, please refer to:
- [Jitsi Meet Documentation](https://jitsi.github.io/handbook/)
- [DigitalOcean Documentation](https://docs.digitalocean.com/)
- [METUnic Documentation](https://app.metunic.com.tr/client/login/)
- [Ubuntu Server Guide](https://ubuntu.com/server/docs)
- [Let's Encrypt Documentation](https://letsencrypt.org/docs/)
