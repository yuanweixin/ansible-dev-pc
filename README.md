# Debian dev machine setup 

This sets up the dev machine, including things like .bashrc (it is overwritten). 

Text shell customization assumes you're using bash.

# Pre-Requisites

1. Make sure you're up to date:

   ```shell
   $ sudo apt update
   $ sudo apt -y upgrade
   ```

2. Install Ansible:

   ```shell
   $ sudo apt -y install ansible
   ```

# Running

Run this in your Qubes app vm in order. 
```shell
$ ansible-playbook -K 1-install.yaml
$ ansible-playbook -K 2-customize.yaml
```

