[<img src="logo.png" align="right">](https://www.merhylstudio.fr)

# Merhylstudio HomeLab <img src="https://img.shields.io/badge/pve-v5.0-brightgreen.svg" alt="Supported Distribution">

> Ansible playbook for a Proxmox HomeLab with pci-passthrough


## Roles

#### :symbols: Proxmox

*TODO*
This role run initial configuration on proxmox host(s).

**Variables:**

**Keys** | **Default value**
---- | -------------
ssh_action_user | billy
ssh_authorized_key_files | -

**Exemple:**
```yml
- hosts: all
  roles:
    - proxmox
```
> :memo: **Note:**
> Set your own values.

## Run

This repository needs some changes to fit your needs:

**Edit inventory**
```
myhost ansible_host=his_ipv4 ansible_port=22 ansible_user=root

[pve]
myhost
```

**Edit hosts vars**
```
myhost ansible_host=his_ipv4 ansible_port=22 ansible_user=root

[pve]
myhost
```

**Run playbook**
```bash
ansible-playbook --ask-pass pb-homelab.yml
```

**Remove last SSH host key**
```bash
ssh-keygen -f ~/.ssh/known_hosts -R 192.168.1.12
```
