# EpicBook Full-Stack Infrastructure

Complete infrastructure automation for deploying the EpicBook application on Azure using Infrastructure as Code (IaC) best practices.

## 📋 Overview

This project provides end-to-end automation for deploying a web application with:
- **Terraform** for Azure infrastructure provisioning
- **Ansible** for configuration management and application deployment
- **Nginx** as a reverse proxy
- Modular, reusable role-based structure

## 🏗️ Architecture

- **Cloud Provider**: Microsoft Azure
- **Web Server**: Nginx (reverse proxy)
- **Application**: EpicBook service (systemd managed)
- **Automation**: Terraform + Ansible
- **Configuration Management**: Ansible roles with Jinja2 templates

## 📂 Project Structure
```
.
├── ansible/
│   ├── ansible.cfg           # Ansible configuration
│   ├── inventory.ini         # Dynamic inventory
│   ├── site.yml             # Main playbook
│   ├── group_vars/
│   │   └── web.yml          # Group variables
│   └── roles/
│       ├── common/          # Common setup tasks
│       ├── epicbook/        # Application deployment
│       └── nginx/           # Nginx configuration
├── terraform/
│   └── main.tf              # Azure infrastructure definition
└── images/                  # Documentation screenshots
```

## 🚀 Quick Start

### Prerequisites

- Terraform >= 1.0
- Ansible >= 2.9
- Azure CLI configured
- SSH access to target hosts

### 1. Provision Infrastructure
```bash
cd terraform
terraform init
terraform plan
terraform apply
```

### 2. Configure and Deploy Application
```bash
cd ../ansible
ansible-playbook -i inventory.ini site.yml
```

## 🔧 Configuration

### Terraform Variables

Edit `terraform/main.tf` to customize:
- Resource group name
- VM size and specifications
- Network configuration
- Storage settings

### Ansible Variables

Configure in `ansible/group_vars/web.yml`:
- Application settings
- Service ports
- User permissions

## 📦 Ansible Roles

### Common Role
- System updates
- Base package installation
- Security configurations

### EpicBook Role
- Application deployment
- Systemd service configuration
- User and permission management

### Nginx Role
- Nginx installation
- Reverse proxy configuration
- SSL/TLS setup (if applicable)

## 🖼️ Screenshots

Project documentation and deployment screenshots are available in the `images/` directory.

## 🛠️ Technologies Used

- **Terraform**: Infrastructure provisioning
- **Ansible**: Configuration management
- **Azure**: Cloud platform
- **Nginx**: Web server/reverse proxy
- **Systemd**: Service management
- **Jinja2**: Template engine

## 📝 Best Practices Implemented

- ✅ Infrastructure as Code (IaC)
- ✅ Idempotent configuration management
- ✅ Role-based organization
- ✅ Variable separation for flexibility
- ✅ Template-driven configuration
- ✅ Modular and reusable components

## 🔒 Security Notes

- Terraform state files are excluded from version control
- Sensitive variables should be managed using environment variables or secret management tools
- SSH keys should be properly secured
- Regular security updates via the common role

## 📖 Usage

1. Clone the repository
2. Configure Azure credentials
3. Update variables in `terraform/main.tf` and `ansible/group_vars/web.yml`
4. Run Terraform to provision infrastructure
5. Run Ansible playbook to configure and deploy

## 🤝 Contributing

Contributions are welcome! Please feel free to submit issues or pull requests.

## 📄 License

This project is open source and available under the MIT License.

## 👤 Author

**Aduroja Akintade**
- GitHub: [@Dudubynatur3](https://github.com/Dudubynatur3)

---

⭐ Star this repo if you find it helpful!
