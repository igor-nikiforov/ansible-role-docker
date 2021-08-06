# Ansible Role: Docker

## Description

This role install and configures Docker.

## Requirements

Ansible >= 2.10

OS:

- Debian
- Ubuntu
- RHEL / CentOS

## Variables

| Name                                                                                                                   | Description                                      | Default  |
|------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------|----------|
| <a name="docker_install"></a> [docker_install](#variable\_docker_install)                                              | If True, Docker will be installed                | `True`   |
| <a name="docker_version"></a> [docker_install](#variable\_docker_install)                                              | Docker version                                   | `latest` |
| <a name="docker_daemon_config"></a> [docker_daemon_config](#variable\_docker_daemon_config)                            | Docker daemon configuration                      | `{}`     |
| <a name="docker_users"></a> [docker_users](#variable\_docker_users)                                                    | List of users to be added to docker group        | `[]`     |
| <a name="docker_sdk_for_python_install"></a> [docker_sdk_for_python_install](#variable\_docker_sdk_for_python_install) | If True, Docker SDK for Python will be installed | `False`  |
| <a name="docker_sdk_for_python_version"></a> [docker_sdk_for_python_version](#variable\_docker_sdk_for_python_version) | Docker SDK for Python version                    | `latest` |
| <a name="docker_compose_install"></a> [docker_compose_install](#variable\_docker_compose_install)                      | If True, Docker Compose will be installed        | `False`  |
| <a name="docker_compose_version"></a> [docker_compose_version](#variable\_docker_compose_version)                      | Docker Compose version                           | `latest` |

## Example

1. Install requirements

```shell
ansible-galaxy install igor_nikiforov.docker
```

2. Run playbook

```shell
ansible-playbook playbook.yml
```

```yaml
# playbook.yml
---
- hosts: all
  become: true

  roles:
    - igor_nikiforov.docker

  vars:
    docker_sdk_for_python_install: False
    docker_compose_install: False
    docker_daemon_config:
      default-address-pools:
        - { base: 172.16.0.0/16, size: 26 }
      log-driver: "json-file"
      log-opts:
        max-size: "10m"
        max-file: "3"
```

## License

Apache
