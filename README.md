geoip Role
=========

This role installs the `geoipupdate` tool which installs the configured geoip databases. It also installs required packages to use geoip with nginx.
It is recommended to run geoipupdate via a cron task. See the docs - https://dev.maxmind.com/geoip/geoipupdate/

Role Variables
--------------

```
geoip_packages:
  - libmaxminddb0
  - libmaxminddb-dev
  - mmdb-bin
  - geoipupdate

geoip_databases: GeoLite2-Country
geoip_user: "{{ ansible_ssh_user }}"
geoip_config_location: "/home/{{ geoip_user }}/GeoIp.conf"
```

----------------

```
#   requirements.yml
#
#   Example
# - src: https://github.com/ergontech-ansible-roles/geoip
#   version: master
#   name: geoip
```

License
-------

[MIT](LICENSE)