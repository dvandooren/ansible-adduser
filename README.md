# Ansible Role - Add Users

This is just a quick playbook to add users with their passwords and/or their ssh key to a set of serves. This playbook runs are root.

## Step 1: Configure envs/<files>
- Create a `envs/<project>.hosts` file based on `env/sample.hosts` file. Add your servers and IPs to the `[servers]` group.
- Create a `envs/<project>.config` file based on the `envs/sample.config` file to define the needed users and credentials.
    + To generate encrypted passwords for the files see: http://docs.ansible.com/ansible/latest/faq.html#how-do-i-generate-crypted-passwords-for-the-user-module

## Step 2: Run playbook
The first playbook `add_users.yaml` will add the configured users to the server

```Shell
./scripts/env-ansible.sh <project> add_users.yaml --ask-pass
```