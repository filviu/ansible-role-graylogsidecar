# Ansible Role: Graylog Sidecar

[![CI](https://github.com/filviu/ansible-role-graylogsidecar/actions/workflows/ci.yml/badge.svg)](https://github.com/filviu/ansible-role-graylogsidecar/actions/workflows/ci.yml)

Sets up Graylog Sidecar and optionally configures the collector for the node(s) via the Graylog API.

## Requirements / Limitations

- Your configurations need to have **unique names**. I decided to write the role to setup collector configurations using names instead of IDs for readability.
- There is an API limitation that reads X number of configuration per page. I set that number to be 999. If you have more than 999 collector configuration please fix the role to use pagination and open a PR :)
- What I consider [a graylog API bug](https://github.com/Graylog2/graylog2-server/issues/12044) requires admin level access to read sidecars configuration. That's why you need to define a `sidecar_graylog_server_api_admin_token`. If you don't want to configure node collectors using this role than you can skip it. I will remove it once/if the bug is fixed. 

## Role Variables

See `defaults/main.yml`:

    sidecar_graylog_server_api_url: example.com
    sidecar_graylog_server_api_token: xxx
    sidecar_graylog_server_api_admin_token: yyy

    sidecar_config_template: sidecar.yml.j2

    sidecar_collector_config:
      - collector: collector-name
        configuration: collector-config-name

Template file to use for configuration. The default supplied should work very well.

## Dependencies

None.

## Example Playbook

```yaml
---
- hosts: all

  roles:
    - role: filviu.graylogsidecar
      sidecar_graylog_server_api_url: http://1.2.3.4:9000/api/
      sidecar_graylog_server_api_token: xxx
      sidecar_graylog_server_api_admin_token: yyy

      sidecar_collector_config:
        - collector: collector-name
          configuration: collector-config-name
```

## License

MIT / BSD


## Author Information

This role was created by Silviu Vulcan to scratch his own itch.
