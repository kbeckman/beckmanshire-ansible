# beckmanshire-ansible ChangeLog

## [11/6/2025]

* Adds `playbook/time-machine` implementation to configure ignore targets for macOS `Time Machine`.
* Updates `playbook/prerequisites` to provision `~/VMs` directory.
* Fixes `README.md` filename typo.

## [10/13/2025]

* Initial project implementation.
  * `playbooks/asdf` -- Installs and updates `asdf` plugins.
  * `playbooks/homebrew` -- Installs `homebrew` package manager and any defined formulae / casks.
  * `playbooks/oh-my-zsh` -- Installs `oh-my-zsh` and sets default shell to `ZSH`.
  * `playbooks/prereqisites` -- Provisions prerequisite resources (i.e. directories, SSH keys, etc).
