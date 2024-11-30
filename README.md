# Ansible Project

## **Description**
This project demonstrates the use of Ansible to manage and automate server configurations. It includes:
1. A playbook to install necessary packages like `vim` and `zip` on remote nodes.
2. A playbook to deploy a dynamic template file that contains the hostname of each node.

The project uses a role-based structure for better organization.

---

## **Project Structure**
```plaintext
Project/
├── inventory/                # Directory containing inventory files
│   └── hosts.yml             # Inventory file defining nodes
├── playbook.yml              # Main Ansible playbook
├── roles/                    # Directory for roles
│   ├── common/               # Role: common
│   │   ├── tasks/            # Task definitions for the role
│   │   │   ├── main.yml      # Main task file
│   │   │   └── install-vim-zip.yml # Task for installing vim and zip
│   │   ├── files/            # Static files for the role
│   │   ├── templates/        # Jinja2 templates
│   │   ├── vars/             # Variables specific to the role
│   │   ├── meta/             # Metadata for the role
│   │   └── defaults/         # Default variables for the role
│   └── deploy_template/      # Role: deploy_template
│       ├── tasks/            # Task definitions for the role
│       │   └── main.yml      # Task to deploy a template
│       ├── templates/        # Jinja2 templates
│       │   └── dynamic-hostname # Template file to deploy
│       ├── files/            # Static files for the role
│       ├── vars/             # Variables specific to the role
│       ├── meta/             # Metadata for the role
│       └── defaults/         # Default variables for the role


1) Create Docker Containers for Nodes.
2) Update Inventory: Update inventory/hosts.yml with the correct IP/ports.
3) Copy the inventory file to Ansible's default location (optional):
cp inventory/hosts.yml /etc/ansible/hosts
