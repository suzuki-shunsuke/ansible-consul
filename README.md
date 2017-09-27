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
consul_start_join | no | not specified | ["192.168.33.10"] | [start_join](https://www.consul.io/docs/agent/options.html#start_join)
consul_lib_dir | no | /usr/local/lib | | The install path. This directory is generated if it doesn't exist
consul_bin_dir | no | /usr/local/bin | | The install path. This directory is generated if it doesn't exist
consul_data_dir | no | /tmp/consul | | [-data-dir](https://www.consul.io/docs/agent/options.html#_data_dir). This directory is generated if it doesn't exist
consul_config_file | no | /etc/consul/consul.json | | [-config-file](https://www.consul.io/docs/agent/options.html#_config_file). This parent directory is generated if it doesn't exist
consul_bootstrap_expect | no | not specified | | [-bootstrap-expect](https://www.consul.io/docs/agent/options.html#_bootstrap_expect)
consul_node | no | `ansible_hostname` | | [-node](https://www.consul.io/docs/agent/options.html#_node)
consul_is_server | no | no | yes | [-server](https://www.consul.io/docs/agent/options.html#_server)
consul_enabled | no | undefined (do nothing) | yes/no | whether consul service is enabled
consul_bind | no | `ansible_default_ipv4.address` | "192.168.60.10" | [-bind](https://www.consul.io/docs/agent/options.html#_bind)

## Dependencies

* [suzuki-shunsuke/hashicorp-binary](https://galaxy.ansible.com/suzuki-shunsuke/hashicorp-binary/)

## Example Playbook

```yaml
- hosts: servers
  roles:
  - role: suzuki-shunsuke.consul
    consul_arch: linux_amd64
    consul_version: 0.9.2
    consul_start_join:
    - 192.168.33.10
    - 192.168.33.11
    consul_lib_dir: "{{ansible_env.HOME}}/lib"
    consul_bin_dir: "{{ansible_env.HOME}}/bin"
    consul_data_dir: /tmp/consul
    consul_config_file: /etc/consul/consul.json
    consul_bootstrap_expect: 3
    consul_node: "{{ansible_hostname}}"
    consul_is_server: yes
    consul_enabled: yes
```

## Change Log

See [CHANGELOG.md](CHANGELOG.md).

## Contributing

See [CONTRIBUTING.md](CONTRIBUTING.md).

## License

[MIT](LICENSE)
