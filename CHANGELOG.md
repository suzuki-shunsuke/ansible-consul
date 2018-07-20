# Change Log

All notable changes to this project will be documented in this file. See [standard-version](https://github.com/conventional-changelog/standard-version) for commit guidelines.

<a name="3.0.0"></a>
# [3.0.0](https://github.com/suzuki-shunsuke/ansible-consul/compare/v2.0.3...v3.0.0) (2018-07-20)


### Features

* improve role ([ee7d758](https://github.com/suzuki-shunsuke/ansible-consul/commit/ee7d758))
* remove dependencies ([125ba45](https://github.com/suzuki-shunsuke/ansible-consul/commit/125ba45))



<a name="2.0.3"></a>
## [2.0.3](https://github.com/suzuki-shunsuke/ansible-consul/compare/v2.0.2...v2.0.3) (2017-10-09)


### Bug Fixes

* allow to make consul enabled by systemd ([dcd336e](https://github.com/suzuki-shunsuke/ansible-consul/commit/dcd336e))



<a name="2.0.2"></a>
## [2.0.2](https://github.com/suzuki-shunsuke/ansible-consul/compare/v2.0.1...v2.0.2) (2017-10-07)


### Bug Fixes

* fix invalid variable name ([059461c](https://github.com/suzuki-shunsuke/ansible-consul/commit/059461c))



<a name="2.0.1"></a>
## [2.0.1](https://github.com/suzuki-shunsuke/ansible-consul/compare/v2.0.0...v2.0.1) (2017-10-07)


### Bug Fixes

* fix the collision of the variable name "consul_config_file" ([1cddd17](https://github.com/suzuki-shunsuke/ansible-consul/commit/1cddd17))



<a name="2.0.0"></a>
# [2.0.0](https://github.com/suzuki-shunsuke/ansible-consul/compare/v1.3.0...v2.0.0) (2017-10-07)


### Features

* enable to set all consul's configuration ([23c92e6](https://github.com/suzuki-shunsuke/ansible-consul/commit/23c92e6))


### BREAKING CHANGES

* Some variables are removed. Set them in the `consul_config` variable.

* consul_data_dir: consul_config.data_dir
* consul_node: consul_config.node_name
* consul_is_server: consul_config.server
* consul_bind: consul_config.bind_addr
* consul_bootstrap_expect: consul_config.bootstrap_expect



<a name="1.3.0"></a>
# [1.3.0](https://github.com/suzuki-shunsuke/ansible-consul/compare/v1.2.0...v1.3.0) (2017-09-27)


### Features

* add the variable "consul_bind" ([43faff0](https://github.com/suzuki-shunsuke/ansible-consul/commit/43faff0))



<a name="1.2.0"></a>
# [1.2.0](https://github.com/suzuki-shunsuke/ansible-consul/compare/v1.1.0...v1.2.0) (2017-09-26)


### Features

* allow not to set some parameters ([e52380e](https://github.com/suzuki-shunsuke/ansible-consul/commit/e52380e))



<a name="1.1.0"></a>
# [1.1.0](https://github.com/suzuki-shunsuke/ansible-consul/compare/v1.0.0...v1.1.0) (2017-09-15)


### Features

* set the default value of `consul_start_join` to `ansible_all_ipv4_addresses` ([041792d](https://github.com/suzuki-shunsuke/ansible-consul/commit/041792d))



<a name="1.0.0"></a>
# 1.0.0 (2017-08-21)


### Features

* implement basic function ([0016340](https://github.com/suzuki-shunsuke/ansible-consul/commit/0016340))
