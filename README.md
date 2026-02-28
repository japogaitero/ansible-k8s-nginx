# Automated Kubernetes Portfolio Deployment with Ansible

This project demonstrates **Infrastructure as Code (IaC)** by automating the deployment of a customized Nginx web server onto a **Kubernetes (K8s)** cluster using **Ansible**.



## 🚀 Overview

Instead of manual configurations, this project uses Ansible playbooks to:
1. Create a dedicated **Kubernetes Namespace**.
2. Inject a custom `index.html` via a **ConfigMap**.
3. Deploy an **Nginx** server mounting the custom content.
4. Expose the service to the host machine (Windows) via **NodePort**.

## 🛠️ Tech Stack

* **OS:** Windows 11 with WSL2 (Ubuntu 22.04)
* **Orchestration:** Kubernetes (via Docker Desktop)
* **Automation:** Ansible 2.15+
* **Container Engine:** Docker
* **Language:** Python (for Ansible K8s modules)

## 🛠️ Project Structure

- `deployment.yml`: Main playbook to provision the infrastructure.
- `cleanup.yml`: Playbook to remove all created resources.
- `ansible.cfg`: Global Ansible settings.
- `hosts`: Inventory defining the local connection.

## ⚙️ How to use

1. **Prepare the environment:**
   ```bash
   python3 -m venv venv
   source venv/bin/activate
   pip install kubernetes
   ansible-galaxy collection install kubernetes.core
   
2. **Deploy the application:**
   ansible-playbook deployment.yml

3. **Remove the deployment:**
   ansible-playbook cleanup.yml

Developed as part of my DevOps Portfolio.