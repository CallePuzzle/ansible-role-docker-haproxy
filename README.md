Ansible Role: HaProxy containerized
=========
Deploy a HaProxy in Docker.

Requirements
------------
None.

Role Variables
--------------

* `haproxy_links`: List of links with others services, parameter links in docker_container_module.
* `haproxy_ports`: List of ports to publish from the container to the host, parameter published_ports in docker_container_module.

Dependencies
------------
* geerlingguy.pip
* geerlingguy.docker

Example Playbook
----------------

``` yaml
---
- hosts: all

  vars:
    haproxy_links:
      - httpd
    haproxy_ports:
      - 80:80

  roles:
    - { role: ansible-role-docker-haproxy, tags: ['haproxy'] }
```

License
-------

[GNU v3](LICENSE)
