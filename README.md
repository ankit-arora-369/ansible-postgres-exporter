# Ansible role: ansible-postgres-exporter

Ansible role for installing and configuring [Prometheus Postgres Exporter](https://github.com/wrouesnel/postgres_exporter) with supervisord on Debian based systems only. Tested platforms are:

* Ubuntu 16.04
* Debian 8
* Debian 9

Requirements
------------

No special requirements; requries root access on the desitination hosts. So, become: true

Role Variables
--------------

The variables that can be passed to this role and a brief description about them are as follows. (For all variables, take a look at defaults/main.yml)

```yaml
postgres_exporter_version: v0.8.0
```
installing specific version

```yaml
postgres_exporter_listen_address: ":9187"
```
listen address port

```yaml
postgres_exporter_version_checksum: "272ed14d3c360579d6e231db34a568ec08f61d2e163cf111e713929ffb6db3f5"
```
checksum

```yaml
postgres_exporter_query_directory: "/opt/postgres_exporter/metrics.yaml"
```
directory of queries yaml


```yaml
postgres_exporter_log_level: "info"
```
defining the log level to change the logs from postgres_exporter

```yaml
with_pip: "False"
```
False by default, which installs the supervisor from apt. Mark it "True" if you want to install supervisord using pip and can also tweak the supervisor role which is included.

```yaml
ansible-playbook -i hosts.txt playbook.yml --ask-become-pass -v
```
Above is the example command to execute the playbook.


Author Information
------------------

This role was created in 2020 by Ankit Arora
