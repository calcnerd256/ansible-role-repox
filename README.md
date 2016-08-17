OULibraries.repox
=========

[REPOX](https://github.com/europeana/REPOX "REPOX on github") for [OU Libraries](https://github.com/OULibraries/ "GitHub").

gotchas:
* some ansible variables don't actually support changing at this time
* I'm not sure what `repox_mariadb_privileges` needs to be, but it's currently `ALL`
* `repox_path_source` needs to be a nonexistent immediate subdirectory of an existing directory
* `repox_path_data` needs to be a nonexistent immediate subdirectory of an existing directory
* `repox_path_log` needs to be an existing directory
* no path variable should end with a /
* `repox_source_tag` must be `v3.1.0` or the j2 templates need to change accordingly
* ldap variables are wrong
* `repox_base_urn` is wrong
* smtp variables are wrong

TODO:
  * [finish e-mail configuration and testing](https://github.com/OULibraries/ansible-role-repox/issues/4 "GitHub issue 4")
  * remove default password from role


Requirements
------------

CentOS 7x.

Role Variables
--------------

See defaults/main.yml

Dependencies
------------

* [OULibraries.centos7](https://github.com/OULibraries/ansible-role-centos7 "GitHub repo")
* [OULibraries.repox](https://github.com/OULibraries/ansible-role-repox "GitHub repo")
* [OULibraries.postfix-mta](https://github.com/OULibraries/ansible-role-postfix-mta "GitHub repo")
* [OULibraries.users](https://github.com/OULibraries/ansible-role-users "GitHub repo")

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

* Montana Rowe
* Jason Sherman
