# ansible-consul

ansible role to install consul as a systemd service

https://galaxy.ansible.com/suzuki-shunsuke/consul/

## Notice

Please use this role rather than [suzuki-shunsuke.consul-linux](https://galaxy.ansible.com/suzuki-shunsuke/consul-linux/).

## Requirements

* systemd

## Role Variables

name | required | default | example | description
--- | --- | --- | --- | ---
consul_arch | yes | | linux_amd64, darwin_amd64, etc |
consul_version | yes | | 0.9.2 | installed binary version
consul_lib_dir | no | /usr/local/lib | | The install path. This directory is generated if it doesn't exist
consul_bin_dir | no | /usr/local/bin | | The install path. This directory is generated if it doesn't exist
consul_config_file | no | /etc/consul/consul.json | | [-config-file](https://www.consul.io/docs/agent/options.html#_config_file). This parent directory is generated if it doesn't exist
consul_enabled | no | undefined (do nothing) | yes/no | whether consul service is enabled
consul_config | no | {} | |
consul_default_config | no | see [defaults/main.yml](defaults/main.yml) | |

## Dependencies

* [suzuki-shunsuke/hashicorp-binary](https://galaxy.ansible.com/suzuki-shunsuke/hashicorp-binary/)

## Example Playbook

```yaml
- hosts: servers
  roles:
  - role: suzuki-shunsuke.consul
    consul_arch: linux_amd64
    consul_version: 0.9.3
    consul_lib_dir: "{{ansible_env.HOME}}/lib"
    consul_bin_dir: "{{ansible_env.HOME}}/bin"
    consul_config_file: /etc/consul/consul.json
    consul_enabled: yes
    consul_config:
      start_join:
        - 192.168.33.10
        - 192.168.33.11
      bootstrap_expect: 3
      node_name: "{{ansible_hostname}}"
      server: true
      data_dir: /tmp/consul
```

## Change Log

See [CHANGELOG.md](CHANGELOG.md).

## Contributing

See [CONTRIBUTING.md](CONTRIBUTING.md).

## License

[MIT](LICENSE)
