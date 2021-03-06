## linuxmuster_net-server-customize

<!-- This file was generated by Ansigenome. Do not edit this file directly but
     instead have a look at the files in the ./meta/ directory. -->

[![Travis CI](http://img.shields.io/travis/ypid/ansible-linuxmuster_net-server-customize.svg?style=flat)](http://travis-ci.org/ypid/ansible-linuxmuster_net-server-customize)
[![Ansible Galaxy](http://img.shields.io/badge/galaxy-ypid.linuxmuster_net–server–customize-660198.svg?style=flat)](https://galaxy.ansible.com/detail#/role/4054)
[![Platforms](http://img.shields.io/badge/platforms-debian%20/%20ubuntu-lightgrey.svg?style=flat)](https://galaxy.ansible.com/detail#/role/4054)
[![GitHub Tags](https://img.shields.io/github/tag/ypid/ansible-linuxmuster_net-server-customize.svg)](https://github.com/ypid/ansible-linuxmuster_net-server-customize)
[![GitHub Stars](https://img.shields.io/github/stars/ypid/ansible-linuxmuster_net-server-customize.svg)](https://github.com/ypid/ansible-linuxmuster_net-server-customize)


Apply common customizations to a linuxmuster.net server.

See [linuxmuster.net](https://linuxmuster.net) for more information.

Features:

* Put [Linbo](https://de.wikipedia.org/wiki/LINBO) configuration files under version control.
* Generate Linbo start.conf configuration via Ansible/Jinja2 templating.
* Install additional packages to create database SQL dumps on an regular bases.

### Installation

This role requires at least Ansible `v1.3`. To install it, run:

```Shell
ansible-galaxy install ypid.linuxmuster_net-server-customize
```

To install via git, run either:

```Shell
git clone https://github.com/ypid/ansible-linuxmuster_net-server-customize.git ypid.linuxmuster_net-server-customize
git submodule add https://github.com/ypid/ansible-linuxmuster_net-server-customize.git ypid.linuxmuster_net-server-customize
```



### Role variables

List of default variables available in the inventory:

```YAML
---

## Set default partition sizes for operation systems in GiB.
linuxmuster_net_server_customize_default_partition_size:

  linux: 50
  ## Imaging will take longer because of zeroing …
  ## Maybe consider creating an specific system group for imaging with a small partition.

  cache: 30
  swap: 2

linuxmuster_net_server_customize_default_auto_partition: 'no'
linuxmuster_net_server_customize_default_auto_format: 'no'
linuxmuster_net_server_customize_default_auto_init_cache: 'no'

# linuxmuster_net_server_customize_default_auto_partition: 'no'
# linuxmuster_net_server_customize_default_auto_partition: 'yes'
# linuxmuster_net_server_customize_default_auto_format: '{{ linuxmuster_net_server_customize_default_auto_partition }}'
# linuxmuster_net_server_customize_default_auto_init_cache:  '{{ linuxmuster_net_server_customize_default_auto_partition }}'

## The cache partition is the last partition and will end at the end of the block device if the following is true.
## If false, only the space specified by linuxmuster_net_server_customize_default_partition_size.cache will be used.
## This might result in unused space on the block device.
linuxmuster_net_server_customize_use_max_cache_partition: True

linuxmuster_net_server_customize_default_download_type: 'rsync'
linuxmuster_net_server_customize_default_autostart: 'yes'
linuxmuster_net_server_customize_default_autostart_timeout: 5

linuxmuster_net_server_customize_default_action: 'start'
# linuxmuster_net_server_customize_default_action: 'sync'
# linuxmuster_net_server_customize_default_action: 'new'


linuxmuster_net_server_customize_system_groups:
  # - name: 'hp10'
  #
  # - name: 'test'

  #   # AutoPartition: 'yes'
  #   # AutoFormat: 'yes'
  #   # AutoInitCache: 'yes'

  #   Autostart: 'yes'
  #   AutostartTimeout: 5
  #   DefaultAction: 'start'
  #   os_partition_size: 120


linuxmuster_net_server_apt_packages:
  - 'autopostgresqlbackup'
  - 'automysqlbackup'
linuxmuster_net_server_apt_packages_group:
linuxmuster_net_server_apt_packages_host:
```




### Authors and license

`linuxmuster_net-server-customize` role was written by:

- [Robin Schneider](http://ypid.de/) | [e-mail](mailto:ypid@riseup.net) | [Twitter](https://twitter.com/ypid) | [GitHub](https://github.com/ypid)

License: [AGPLv3](https://tldrlegal.com/license/gnu-affero-general-public-license-v3-%28agpl-3.0%29)

***

README generated by [Ansigenome](https://github.com/nickjj/ansigenome/).
