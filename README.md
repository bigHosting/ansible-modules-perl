# ansible-modules-perl

Ansible repository for my own modules written in perl

##### ansible -k --ask-become-pass --become-method=sudo webserver1.domain.com *-m rpm_version -a name=openssh* -u USER
```
SSH password: 
webserver1.domain.com | success >> {
    "changed": "False",
    "name": "openssh",
    "release": "2.el6",
    "version": "7.4p1"
}
```

##### ansible-playbook -k --ask-become-pass --become-method=sudo -l webserver1.domain.com -u USER /etc/ansible/playbooks/rpm_version.yml
```
PLAY [all] ******************************************************************** 

GATHERING FACTS *************************************************************** 
ok: [webserver1.domain.com]

TASK: [rpm version for openssh] *********************************************** 
changed: [webserver1.domain.com] => (item=openssh-server)

TASK: [rpm_version - print info] ********************************************** 
ok: [webserver1.domain.com] => {
    "var": {
        "openssh_server_version": {
            "changed": false, 
            "msg": "All items completed", 
            "results": [
                {
                    "changed": "False", 
                    "invocation": {
                        "module_args": "name=openssh-server", 
                        "module_complex_args": {}, 
                        "module_name": "rpm_version"
                    }, 
                    "item": "openssh-server", 
                    "name": "openssh-server", 
                    "release": "2.el6", 
                    "version": "7.4p1"
                }
            ]
        }
    }
}

PLAY RECAP ******************************************************************** 
webserver1.domain.com    : ok=3    changed=0    unreachable=0    failed=0 
```
