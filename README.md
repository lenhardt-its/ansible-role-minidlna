# Ansible Role: Minidlna

[![ubuntu-18](https://img.shields.io/badge/ubuntu-18.x-orange?style=flat&logo=ubuntu)](https://ubuntu.com/)
[![ubuntu-20](https://img.shields.io/badge/ubuntu-20.x-orange?style=flat&logo=ubuntu)](https://ubuntu.com/)
[![debian-9](https://img.shields.io/badge/debian-9.x-orange?style=flat&logo=debian)](https://www.debian.org/)
[![debian-10](https://img.shields.io/badge/debian-10.x-orange?style=flat&logo=debian)](https://www.debian.org/)

[![License](https://img.shields.io/badge/license-MIT%20License-brightgreen.svg?style=flat)](https://opensource.org/licenses/MIT)
[![GitHub issues](https://img.shields.io/github/issues/OnkelDom/ansible-role-minidlna?style=flat)](https://github.com/OnkelDom/ansible-role-minidlna/issues)
[![GitHub tag](https://img.shields.io/github/tag/OnkelDom/ansible-role-minidlna.svg?style=flat)](https://github.com/OnkelDom/ansible-role-minidlna/tags)
[![GitHub action](https://github.com/OnkelDom/ansible-role-minidlna/workflows/ansible-lint/badge.svg)](https://github.com/OnkelDom/ansible-role-minidlna)

## Description

Deploy and manage Prometheus [minidlna](https://help.ubuntu.com/community/MiniDLNA) service using ansible.

## Requirements

- Ansible >= 2.9 (It might work on previous versions, but we cannot guarantee it)

## Role Variables

All variables which can be overridden are stored in [defaults/main.yml](defaults/main.yml) file as well as in table below.

| Name           | Default Value | Description                        |
| -------------- | ------------- | -----------------------------------|
| `proxy_env` | {} | Proxy environment variables for Client|
| `minidlna_version` | 1.3.0 | MiniDLNA package version. Also accepts `latest` as parameter. |
| `minidlna_config_file` | /etc/minidlna.conf | Config path |
| `minidlna_log_dir` | "/var/log/minidlna" | Log path |
| `minidlna_db_dir` | "/var/cache/minidlna" | DB dir |
| `minidlna_system_user` | "minidlna" | Default user |
| `minidlna_system_group` | "minidlna" | Default group |
| `minidlna_media_dirs` | {} | Media directorys |
| `minidlna_album_art_dirs` | {} | Album art directorys |
| `minidlna_merge_media_dirs` | "no" |  |
| `minidlna_root_container` | "." |  |
| `minidlna_network_interface` | "{{ ansible_default_ipv4.interface }}" |  |
| `minidlna_serial` | "{{ ansible_default_ipv4.macaddress }}" |  |
| `minidlna_port` | 9500 |  |
| `minidlna_presentation_url` | "/" |  |
| `minidlna_friendly_name` | "{{ ansible_hostname }}" |  |
| `minidlna_model_name` | "Windows Media Connect compatible (MiniDLNA)" |  |
| `minidlna_inotify` | "yes" |  |
| `minidlna_strict_dlna` | "no" |  |
| `minidlna_enable_tivo` | "no" |  |
| `minidlna_tivo_discovery` | "bonjour" |  |
| `minidlna_notify_interval` | 90 |  |
| `minidlna_minissdpdsocket` | "" |  |
| `minidlna_force_sort_criteria` | "" |  |
| `minidlna_max_connections` | 5 |  |
| `minidlna_wide_links` | "yes" |  |

## Example

### Playbook

```yaml
- hosts: all
  roles:
    - onkeldom.minidlna
```

## Contributing

See [contributor guideline](CONTRIBUTING.md).

## License

This project is licensed under MIT License. See [LICENSE](/LICENSE) for more details.
