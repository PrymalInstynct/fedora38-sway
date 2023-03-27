# fedora38-sway

## Description

This is an ansible role to configure the Fedora 38 Sway Spin after installation is complete

This includes installing a few software dependencies, FlatPaks, and VSCode Extensions. As well as configuring the Sway Window Manager

## Dependencies

### Software

- ansible-core

  `sudo dnf -y install ansible-core`

### Ansible Collections

- community.general

  `ansible-galaxy collection install -r requirements.yml`

## Inventory & Variables

Create an inventory.yml file at the top level of this Project

```yaml
---
all:
  hosts:
    localhost:
      ansible_hostname: 127.0.0.1
      ansible_user: user
      git_username: awesomeuser
      git_email: awesomeuser@taco.johns
      vscode_exentions:
        - rocketseat.theme-omni
        - esbenp.prettier-vscode
        - dbaeumer.vscode-eslint
        - golang.go
        - ms-vscode.cmake-tools
        - HashiCorp.terraform
        - britesnow.vscode-toggle-quotes
        - mitchdenny.ecdc
        - ms-kubernetes-tools.vscode-kubernetes-tools
        - oderwat.indent-rainbow
        - redhat.ansible
        - signageos.signageos-vscode-sops
        - usernamehw.errorlens
        - fcrespo82.markdown-table-formatter
        - ms-vscode-remote.remote-ssh
        - ms-vscode-remote.remote-ssh-edit
        - ms-vscode-remote.remote-containers
```

## Usage

Copy or Symlink role to /etc/ansible/roles

`sudo ln -s roles/fedora-sway-config /etc/ansible/roles`

`ansible-playbook -i inventory.yml playbooks/config-fedora-sway.yml -K`
