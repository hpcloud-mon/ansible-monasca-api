#monasca-api
Installs the [monasca-api](https://github.com/stackforge/monasca-api) part of the [Monasca](https://wiki.openstack.org/wiki/Monasca) project.

##Requirements
- api_region 
- influxdb_host
- influxdb_user
- influxdb_password
- kafka_hosts - comma separated list of host:port combinations
- keystone_host
- keystone_admin
- keystone_admin_password
- mysql_host
- mysql_user
- mysql_password
- zookeeper_hosts - comma separated list of host:port combinations

##Optional parameters
These all default to an empty value
- keystone_admin_token
- monasca_api_truststore - The role will not upload this file it must be put in place before the role is run
- monasca_api_truststore_password

##Example Playbook

    hosts: monasca
    sudo: yes
    roles:
      - {role: tkuhlman.monasca-api,
         influxdb_user: "{{api_influxdb_user}}",
         influxdb_password: "{{api_influxdb_password}}",
         mysql_user: "{{api_mysql_user}}",
         mysql_password: "{{api_mysql_password}}",
         tags: [api]}

##License
Apache

##Author Information
Tim Kuhlman
Monasca Team email monasca@lists.launchpad.net
