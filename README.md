# Ansible Homebrew

[Ansible](https://www.ansible.com) role that installs [Homebrew](http://brew.sh), an OS X package manager.



## Role Variables

* `homebrew_user` (or `user`) - **required** - The user for which Homebrew will be installed, presumably an administrator of the machine (defaults to the value of the `user` variable).
* `homebrew_dir` - The directory where Homebrew will be installed (defaults to `/usr/local`).
* `homebrew_repo` - The repository to clone Homebrew from (defaults to `https://github.com/Homebrew/brew.git`).
* `homebrew_taps` `[array]` - Additional Homebrew formulae repositories to tap (defaults to `homebrew/dupes` and `homebrew/services`).



## Example Playbook

    - hosts: servers
      roles:
        - role: AlphaHydrae.homebrew
          homebrew_user: jdoe

**With a default user defined (e.g. at the playbook level)**

    - hosts: servers
      vars:
        user: jdoe
      roles:
        - role: AlphaHydrae.homebrew
