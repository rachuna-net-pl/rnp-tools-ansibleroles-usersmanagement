rnp-tools-ansibleroles-usersmanagement
=========

Ansible Role - System Users Management

![Overwiew](https://gitlab.com/rachuna-net.pl/tools/ansibleroles/rnp-tools-ansibleroles-sethostname/-/raw/develop/docs/userManagement.png)

Role Variables
--------------

Defaults role values:
```
input_role_technical_accounts:
  - username: ansible_tech_user
    comment: "Ansible - technical user account"
    shell: /bin/bash
    system_groups: sudo
    uid: 20001
    gid: 20000
    public_ssh_key:  ""
    private_ssh_key: ""

input_role_user_accounts:
  - username: defaultuser
    comment: "Default User"
    shell: /bin/bash
    gid: 1000
    public_ssh_key: ""
    private_ssh_key: ""
    authorized_keys: []

input_role_users_on_host:
  - username: defaultuser
    system_groups:
      - sudo
      - docker
```

Role vars
```
var_defeault_shell: /bin/bash
```

Example Playbook
----------------

```
    - hosts: servers
      become: yes
      tasks:
        - include_role:
            name: rnp-tools-ansible-roles-usersmanagement
          vars:
            input_role_technical_accounts:
              - username: ansible_tech_user
                comment: "Ansible - technical user account"
                shell: /bin/bash
                system_groups: sudo
                uid: 20001
                gid: 20000
                public_ssh_key:  ""
                private_ssh_key: ""
            input_role_user_accounts:
              - username: defaultuser
                comment: "Default User"
                shell: /bin/bash
                gid: 1000
                public_ssh_key: ""
                private_ssh_key: ""
                authorized_keys: []
            input_role_users_on_host:
              - username: defaultuser
                system_groups:
                  - sudo
                  - docker
```

License
-------

BSD 3-Clause

Author Information
------------------

### Maciej Rachuna
SysOps/DevOps
