# ansible-consul

ansible role to install consul as a systemd service

https://galaxy.ansible.com/suzuki-shunsuke/consul/

## Note

Please use this role rather than [suzuki-shunsuke.consul-linux](https://galaxy.ansible.com/suzuki-shunsuke/consul-linux/).

## Requirements

* systemd

## Role Variables

name | required | default | example | description
--- | --- | --- | --- | ---
consul_arch | yes | | linux_amd64, darwin_amd64, etc |
consul_version | yes | | 1.2.0 | installed binary version

And please see

* [defaults/main.yml](defaults/main.yml)
* [vars/main.yml](vars/main.yml)

## Example Playbook

```yaml
- hosts: servers
  roles:
  - role: suzuki-shunsuke.consul
    consul_arch: linux_amd64
    consul_version: 1.2.0
    consul_config:
      start_join:
      - 192.168.33.10
      - 192.168.33.11
      bootstrap_expect: 3
      node_name: "{{ansible_hostname}}"
      data_dir: /tmp/consul
    consul_config_files:
      web:
        service:
          name: web
          tags:
          - rails
          port: 80
    become: yes
```

## Change Log

See [CHANGELOG.md](CHANGELOG.md).

## Contributing

See [CONTRIBUTING.md](CONTRIBUTING.md).

## License

[MIT](LICENSE)
