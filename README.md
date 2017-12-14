# Ansible Role: Install [traefik](https://traefik.io/) proxy as a Docker container

An Ansible role to install traefik proxys as a Docker container.

## Requirements

This role requires Ansible 1.2 or higher.

## Role variables

Ansible variables are listed below with their default values.

```
traefik_certificates: []
traefik_docker_domain
traefik_group: root
traefik_dir: /etc/traefik
traefik_network: traefik
traefik_user: root
traefik_volumes: []
traefik_enable_web: false

traefik_acme_email: "me@google.com"
traefik_acme_on_demand: false
traefik_acme_domains:
  - domain: mydomain.com
    sans:
      - www.mydomain.com
```

## Example playbook

```
---
- hosts: webservers
  roles:
    - sfl.docker-traefik
      traefik_certificates:
      -
      	{
      		CertFile: "/path/to/certificate.crt",
      		KeyFile: "/path/tto/keyfile.key"
      	}
      traefik_docker_domain: mydomain.com
      traefik_network: mydomain
      traefik_volumes:
      - /etc/ssl:/etc/ssl
```

## License

MIT
