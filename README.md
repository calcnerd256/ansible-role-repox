OULibraries.repox
=========

[REPOX](https://github.com/europeana/REPOX "REPOX on github") for OU Libraries.

gotchas:
 some ansible variables don't actually support changing at this time
  I'm not sure what db.privileges needs to be
  repox_path_source needs to be a nonexistent immediate subdirectory of an existing directory
  repox_path_data needs to be a nonexistent immediate subdirectory of an existing directory
  repox_path_log needs to be an existing directory
  no path should end with a /
  repox_source_tag must be v3.1.0 or the j2 templates need to change accordingly
  ldap is wrong
  repox_base_urn is wrong
  smtp is wrong

TODO:
  * finish e-mail configuration and testing
  * test with SELinux
  * remove default password from role
  * remove remaining vagrant-specific bits.


Requirements
------------

CentOS 7x.

Role Variables
--------------

See defaults/main.yml

Dependencies
------------

OULibraries.centos7
OULibraries.repox
OULibraries.postfix-mta
OULibraries.users

Example Playbook
----------------


```
- hosts: servers
  sudo: yes
  vars_files:
    - my-vars.yml
  roles:
    - OULibraries.centos7
    - OULibraries.repox
    - OULibraries.users
```

License
-------

TBD

Author Information
------------------

Montana Rowe
