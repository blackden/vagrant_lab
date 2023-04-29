# Vagrant Lab

This is a Vagrant configuration file for setting up a lab environment with two VMs: one running Ubuntu and the other running CentOS.

- [Vagrant Lab](#vagrant-lab)
  - [Prerequisites](#prerequisites)
  - [Usage](#usage)
  - [Configuration](#configuration)
  - [Authors](#authors)
  - [License](#license)

## Prerequisites

Before you can use this configuration file, you must have the following installed on your system:

- [Vagrant](https://www.vagrantup.com/)
- [VirtualBox](https://www.virtualbox.org/)

## Usage

1. Clone this repository to your local machine.
2. Navigate to the cloned directory.
3. Run the command `vagrant up`.

This will spin up two VMs, one running Ubuntu and the other running CentOS, each with their own configuration.

## Configuration

The Vagrantfile contains the following configuration:

- Ubuntu VM:
  - Box: `ubuntu/focal64`
  - Network: Public network with IP address `192.168.1.121`
  - Provisioner: Ansible playbook `playbook.yml`
- CentOS VM:
  - Box: `centos/7`
  - Network: Public network with IP address `192.168.1.131`
  - Provisioner: Shell script to install packages and configure the environment.

## Authors

- [Your Name](https://github.com/yourname)

## License

This project is [licensed](LICENSE).
