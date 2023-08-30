ansible-bht
=========

An ansible role for managing the installation of `bht`.

More information on `bht` tool can be found at:

  - [https://github.com/ezonakiusagi/bht](https://github.com/ezonakiusagi/bht)


Requirements
------------

This role requires git to be installed on the target system.

Role Variables
--------------

The following variables will change the behavior of this role (default values
are shown below):

```yaml
# The source repository url for bht
bht_repo_source: 'https://github.com/ezonakiusagi/bht.git'

# The source repository revision for bht
bht_repo_revision: master

# The directory where source repository is cloned
bht_repo_directory: '/opt/bht-repository'

# The directory where `bht` executable is installed
bht_install_directory: '/opt/bht'

# The directory where `bht` tool will write its reports
bht_home_directory: '/var/lib/bht'

# The systems' binary directory where `bht` executable will be linked to make is avalible on PATH
bht_binary_directory: '/usr/local/bin'
```

Example Playbook
----------------

```yaml
- hosts: all
  roles:
    - role: rehanone.bht
      vars:
        bht:
          debug: true
          state: present
          install_directory: '/opt/bht'
          home_directory: '/var/lib/bht'
          binary_directory: '/usr/local/bin'
          repo_directory: '/opt/bht-repository'
          repo_source: 'https://github.com/ezonakiusagi/bht.git'
          repo_revision: master
      when: bht_manage
```

License
-------

Apache-2.0
