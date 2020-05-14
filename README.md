Stouts.statsd
=============

[![Build Status](http://img.shields.io/travis/Stouts/Stouts.statsd.svg?style=flat-square)](https://travis-ci.org/Stouts/Stouts.statsd)
[![Galaxy](http://img.shields.io/badge/galaxy-Stouts.statsd-blue.svg?style=flat-square)](https://galaxy.ansible.com/list#/roles/1969)

Ansible role which help you with:

* Install and setup [Statsd](https://github.com/etsy/statsd/)

#### Variables

```yaml
statsd_enabled: yes                 # Enable the role
statsd_home: /opt/statsd            # Where to install

statsd_port: 8125                   # StatsD listening port
statsd_graphiteHost: 127.0.0.1      # Hostname or IP of Graphite server
statsd_graphitePort: 2003           # Line Receiver port of Graphite (Carbon)
statsd_backends:                    # Enabled backends
- ./backends/graphite
statsd_debug: false
statsd_address: 0.0.0.0             # address to listen on over UDP
statsd_address_ipv6: false          # defines if the address is an IPv4 or IPv6 address [true or false]
statsd_mgmt_address: 0.0.0.0        # address to run the management TCP interface on
statsd_mgmt_port: 8126              # port to run the management TCP interface on
statsd_title: statsd                # Allows for overriding the process title
statsd_healthStatus: up             # default health status to be returned and statsd process starts ['up' or 'down']
statsd_flushInterval: 10000         # interval (in ms) to flush to Graphite
statsd_percentThreshold: 90
statsd_flush_counts: true           # send stats_counts metrics
statsd_graphite:
  legacyNamespace: false

statsd_additional_options: {}       # Setup additional options

# Extra NPM dependencies. For example if your config.js depends on to something
# if version package is omitted, assumes current version available at npm
# { name: pkg, version: "1.2.3" }
statsd_extra_dependencies: []
```


#### Usage

Add `Stouts.statsd` to your roles and set vars in your playbook file.

Example:

```yaml

- hosts: all

  roles:
    - Stouts.statsd

  vars:
    statsd_graphiteHost: g.myhost.com
```

#### License

Licensed under the MIT License. See the LICENSE file for details.

#### Feedback, bug-reports, requests, ...

Are [welcome](https://github.com/Stouts/Stouts.statsd/issues)!

If you wish to express your appreciation for the role, you are welcome to send
a postcard to:

    Kirill Klenov
    pos. Severny 8-3
    MO, Istra, 143500
    Russia
