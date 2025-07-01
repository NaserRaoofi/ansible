# 🏭 Enterprise Ansible Project

## 🎯 Overview
Production-ready Ansible infrastructure automation following enterprise best practices for multi-environment deployments.

## �️ Project Structure

```
📁 ansible-project/
├── 📄 ansible.cfg                     # Enterprise Ansible configuration
├── 📄 dynamic_inventory.py            # Dynamic inventory for cloud environments
├── 📄 .gitignore                      # Git ignore patterns
├── 📄 CONNECT-STEPS.md                # SSH connectivity setup guide
├── 📄 ENTERPRISE-STRUCTURE.md         # Architecture documentation
│
├── 📁 inventories/                    # Multi-environment inventories
│   ├── 📁 production/
│   │   ├── 📄 hosts                   # Production inventory
│   │   └── 📁 group_vars/
│   │       ├── 📄 all.yml             # Global production variables
│   │       └── 📄 webservers.yml      # Web tier configuration
│   └── 📁 staging/
│       ├── 📄 hosts                   # Staging inventory
│       └── 📁 group_vars/
│           └── 📄 all.yml             # Staging configuration
│
├── 📁 playbooks/                      # Deployment playbooks
│   ├── 📄 site.yml                   # Master orchestration playbook
│   ├── 📄 enterprise-deployment.yml   # Enterprise deployment logic
│   ├── 📄 connect-test.yml           # Connectivity testing
│   └── 📄 install-tools.yml          # DevOps tools installation
│
└── 📁 roles/                          # Reusable Ansible roles (ready for expansion)
```

## 🚀 Quick Start

### 1. Environment Setup
```bash
# Clone the repository
git clone <repository-url>
cd ansible-project

# Install Ansible (if not already installed)
pip install ansible

# Set up SSH keys
cp your-private-key.pem ~/.ssh/
chmod 600 ~/.ssh/your-private-key.pem
```

### 2. Test Connectivity
```bash
# Test staging environment
ansible-playbook -i inventories/staging/hosts playbooks/connect-test.yml

# Test production environment  
ansible-playbook -i inventories/production/hosts playbooks/connect-test.yml
```

### 3. Deploy Infrastructure
```bash
# Deploy to staging
ansible-playbook -i inventories/staging/hosts playbooks/site.yml

# Deploy to production (with confirmation)
ansible-playbook -i inventories/production/hosts playbooks/site.yml --check
ansible-playbook -i inventories/production/hosts playbooks/site.yml
```
- Ansible installed
- SSH access to target servers
- AWS EC2 instance with proper key pair

### Quick Start
```bash
# Test connectivity
ansible-playbook -i inventory connect-test.yml

# Install essential DevOps tools
ansible-playbook -i inventory install-tools.yml

# Install vim editor
ansible-playbook -i inventory install-vim.yml
```

## 🛠️ What's Installed

### DevOps Tools Installed
- **Git** - Version control (v2.47.1)
- **Docker** - Containerization (v25.0.8)
- **vim** - Text editor (v9.1)
- **htop** - System monitoring
- **tree** - Directory structure viewer
- **wget** - File downloads
- **unzip** - Archive extraction

### Services Configured
- Docker service (started and enabled)
- User permissions (ec2-user added to docker group)

## 📋 Server Configuration

**Target Server**: AWS EC2 Instance
- **OS**: Amazon Linux 2023
- **Architecture**: x86_64
- **Memory**: 949MB
- **Storage**: 8GB (6.5GB available)
- **Hostname**: ip-172-31-85-3
- **Private IP**: 172.31.85.3

## 🔐 Security

- SSH key-based authentication
- Private keys excluded from repository
- Proper file permissions enforced (chmod 600)
- Host key checking disabled for lab environment

## 📚 Learning Progress

1. ✅ **Ansible Setup** - Installation and configuration complete
2. ✅ **SSH Connectivity** - Key-based authentication working
3. ✅ **Package Management** - Successfully installing software via Ansible
4. ✅ **Service Management** - Starting and enabling services
5. ✅ **User Management** - Adding users to groups
6. ✅ **Version Control** - Git integration and GitHub deployment

## 🎓 Next Steps

- [ ] Container deployment with Docker
- [ ] Application deployment automation
- [ ] Monitoring and logging setup
- [ ] Multi-environment configuration
- [ ] CI/CD pipeline integration

## 🔧 Connection Details

**SSH Connection**: 
```bash
ssh -i ~/.ssh/ansibletestkey.pem ec2-user@ec2-100-27-28-140.compute-1.amazonaws.com
```

**Ansible Inventory**: Configured for single EC2 instance with both webserver and database roles

---

**Created**: June 29, 2025  
**Last Updated**: July 1, 2025  
**Author**: NaserRaoofi  
**Purpose**: Learning DevOps automation with Ansible
