# Testing Ansible with Vagrant
This section show how to test your Ansible configuration with Vagrant (one machine only here), to catch
early errors in configuration.

The playbook is configured in such a way that the roles are executed only when their corresponding
tags are provided as arguments to Vagrant. This is not a common real-life scenario, but just a
demonstration of some of the capabilities that Ansible offers.

## Requirements
* Ansible
* Vagrant

## Available tags
* `update-distro`
* `unattended-upgrades`

## Runs
* `vagrant up` -> will spin the box and do automatic provisionining but no roles will run
* `vagrant --tags=update-distro up` will start the box and provision the `update-distro` role
* `vagrant --tags=update-distro,unattended-upgrades provision` provision the already running box with the tags provided
* `vagrant destroy` destroy the box
