# Ansible Role: Graylog Sidecar

[![CI](https://github.com/silviuvulcan/ansible-role-graylogsidecar/workflows/CI/badge.svg?event=push)](https://github.com/silviuvulcan/ansible-role-graylogsidecar/actions?query=workflow%3ACI)

Sets up Graylog Sidecar.

## Requirements

None.

## Role Variables

See `defaults/main.yml`:

    sidecar_graylog_server_url: example.com
    sidecar_graylog_server_api_token: xxx

    sidecar_config_template: sidecar.yml.j2

Template file to use for configuration. The default supplied should work very well.

## Dependencies

None.

## Example Playbook

```yaml
---
- hosts: all

  roles:
    - role: filviu.graylogsidecar
      sidecar_graylog_server_url: http://1.2.3.4:9000/api/
      sidecar_graylog_server_api_token: xxx
```

## License

MIT / BSD


## Author Information

This role was created by Silviu Vulcan to scratch his own itch.
