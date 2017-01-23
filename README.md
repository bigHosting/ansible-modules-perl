# ansible-modules-perl

Ansible repository for my own modules written in perl

# ansible -k --ask-become-pass --become-method=sudo webserver1.domain.com -m rpm_version -a name=openssh -u USER
#SSH password: 
#webserver1.domain.com | success >> {
#    "changed": "False",
#    "name": "openssh",
#    "release": "2.el6",
#    "version": "7.4p1"
#}

