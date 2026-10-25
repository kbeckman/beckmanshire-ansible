# beckmanshire-ansible ChangeLog

## [10/24/2026]

* Modifies `ansible.cfg` for local, project specific configuration (isolated from `~/.ansible`).
* Updates project dependencies to latest versions in `requirements.yaml`.
* Updates `asdf` plugin and `homebrew` package/cask installations n `inventory.yaml`.
* Updates `playbook/homebrew` to perform the following on every invocation: update `homebrew` CLI, upgrade all packages,
  upgrade all casks.
* Refactors `playbook/homebrew` "Install Homebrew" from `shell` to `command` task.

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
