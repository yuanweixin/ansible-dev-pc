# Unix-y Developer Machine Setup

This repository contains useful scripts to set up a Unix-y development machine on Debian.

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

The set up assumes use of Qubes, with a template VM that holds the binaries of all the tools, and app vm that hold the customizations.

Concretely, it means you install the tools (e.g. rustc) on the template vm, which makes it available on all app vms that derive from it.

On the app vm, you run the customization stuff, which does things like configure and pull down vs code extensions, all of which would live in the app vm's home folder.

To install on the template vm:

```shell
$ ansible-playbook -K 1-install.yaml
```

To "customize" on the app vm:
```
$ ansible-playbook -K 2-customize.yaml
```

# Notes on differences between Linux distros

I modified this to work with debian. Removed most of the WSL crap and Ubuntu/gnome specific crap from the original code.
