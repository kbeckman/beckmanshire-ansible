# beckmanshire-ansible

This repository contains a collection of `ansible` playbooks targeted at provisioning a macOS development laptop.

## Prerequisites

### Ansible Controller Node

```shell
# Create an SSH key specific for ansible control and copy it to the target node...
ssh-keygen -t ed25519 -b 4096 -C "ansible-controller@kbeckman-mbp.local" -f ~/.ssh/keys/ansible-controller
ssh-copy-id -i ~/.ssh/keys/ansible-controller kbeckman@ansible-target.local

# Required for VSCode plugins...
pip install ansible-dev-tools --no-input
pip install ansible-lint --no-input
```

### Managed Nodes

_Using the macOS `System Settings.app`..._

* Enable SSH access via `General >> Sharing >> Remote Login`
* Modify local hostname via `General >> Sharing`
* Modify computer name via `General >> About`

```shell
# Edit the /etc/sudoers file with the following config to enable password-less SSH access for admins...
# %admin    ALL = (ALL) NOPASSWD:ALL
sudo visudo

# Install macOS command line tools...
xcode-select --install
```

## Usage

```shell
ansible-galaxy install -r requirements.yaml

# Use the --check option to dry-run the operation...
ansible-playbook ./playbooks/prerequisites.yaml --limit <target-node-name>
ansible-playbook ./playbooks/homebrew.yaml --limit <target-node-name>
ansible-playbook ./playbooks/oh-my-zsh.yaml --limit <target-node-name>
ansible-playbook ./playbooks/asdf.yaml --limit <target-node-name>
ansible-playbook ./playbooks/time-machine.yaml --limit <target-node-name>
```
