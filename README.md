NGINX Controller Generate Token
===============================

A role to generate and return an authentication token for NGINX Controller for use in other Roles or within a playbook.

Requirements
------------

[NGINX Controller](https://www.nginx.com/products/nginx-controller/)

Role Variables
--------------

`user_email` - The email adddress of the NGINX Controller user
`user_password` - The password that corresponds to the user_email
`controller_fqdn` - The DNS name of your NGINX Controller installation
`controller_auth_token` - Variable returned by this Role and consumed by others to authenticate to the NGINX Controller API

Dependencies
------------

none

Example Playbook
----------------

```yaml
- hosts: localhost
  gather_facts: no

  vars:
    controller_fqdn: controller.mydomain.com
    user_email: user@example.com
    user_password: mySecurePassword

  tasks:
    - include_role:
        name: nginxinc.nginx-controller-generate-token

    - include_role:
        name: nginxinc.nginx-controller-agent
```

License
-------

[Apache License, Version 2.0](./LICENSE)

Author Information
------------------

brianehlert
