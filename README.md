openssl_altnames
================

An ansible playbook that adds the necessary configuration directives to configure multiple subject alternative (SAN) names in /etc/pki/tls/openssl.cnf, 
the default openssl configuration file on EL 7 or greater.

The playbook uses lineinfile and blockinfile tasks with regular expressions to ensure the required configuration directives such as `[ alt_names ]` section are present.  
Custom markers are used for req_ext and alt_names blocks.

requirements:
-------------
* Gather facts is enabled
* /etc/pki/tls/openssl.cnf file is present
* Ansible user is able to elevate on the target node

running the playbook:
---------------------

```bash
ansible-playbook openssl_altnames/playbook.yml -i inventory.yml --limit host.example.com --user local --become -kK
```
