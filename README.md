# Ubuntu laptop playbook

[![molecule](https://github.com/diodonfrost/ubuntu-laptop-playbook/workflows/molecule/badge.svg)](https://github.com/diodonfrost/ubuntu-laptop-playbook/actions)

This playbook installs and configures most of the software I use on my Ubuntu laptop for Cloud and software development.

## Installation

1.  [Install Ansible](http://docs.ansible.com/intro_installation.html).
2.  Clone this repository to your local drive.
3.  Run 'ansible-galaxy install -r requirements.yml' inside this directory to install required Ansible roles.
4.  Run 'ansible-playbook playbook.yml -K' inside this directory.

### Running a specific set of tagged tasks

You can filter which part of the provisioning process to run by specifying a set of tags using `ansible-playbook --tags` flag.
The tags available:

- aws-cli
- discord
- docker
- jetbrains-toolbox
- minikube
- openjdk
- slack
- spotify
- virtualbox

## Overriding Defaults

```yaml
---
# defaults file for linux-dev-playbook

# Target users to install
# Define target users where to installs and configures software
# Default: all Linux users
user_list: []

# Install awscli.
# Default is true.
awscli_install: true

# Install voice and text chat Discord.
# Default is true.
discord_install: true

# Install Docker.
# Default is true.
docker_install: true

# Install Minikube for deploy local kubernetes cluster
# Default is true
minikube_install: true

# Install shell Oh-My-Zsh.
# Default is true.
ohmyzsh_install: true

# Install Spotify.
# Default is true.
spotify_install: true

# Install Virtualbox.
# Default is true.
virtualbox_install: true
```

## Dependencies

None

## Local Testing

This project uses [Molecule](http://molecule.readthedocs.io/) to aid in the
development and testing.

To develop or test you'll need to have installed the following:

* Linux (e.g. [Ubuntu](http://www.ubuntu.com/))
* [Docker](https://www.docker.com/)
* [Python](https://www.python.org/) (including python-pip)
* [Ansible](https://www.ansible.com/)
* [Molecule](http://molecule.readthedocs.io/)

### Testing with Docker

```shell
# Test Ansible playbook
molecule test

# Create ubuntu:20.04 instance
molecule create

# Apply Ansible playbook
molecule converge

# Launch Ansible tests
molecule verify
```

## License

Apache 2

## Author Information

This role was created in 2018 by diodonfrost.
