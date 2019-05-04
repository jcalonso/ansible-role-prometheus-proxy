# Ansible Role: Prometheus Proxy 

[![Build Status](https://travis-ci.org/jcalonso/ansible-role-prometheus-proxy.svg?branch=master)](https://travis-ci.org/jcalonso/ansible-role-prometheus-proxy)

Install a Prometheus Proxy (agent and/or proxy) using Ansible.
Prometheus Proxy allows you to send metrics to a Prometheus instance when it is behind a firewall.

More info about Prometheus Proxy: https://github.com/pambrose/prometheus-proxy

## Requirements

A Prometheus server.

## Role Variables

To install the Prometheus Proxy (in the same network as your Prometheus server)
```
prometheus_proxy_enabled: true
prometheus_proxy_agent_enabled: false
```

If you want to install the agent (normally outside the Prometheus network):
```
prometheus_proxy_enabled: false
prometheus_proxy_agent_enabled: true
prometheus_proxy_host: "prometheus.example.com"
```

Check `defaults/main.yml` for other available variables/

## Dependencies

```
geerlingguy.java
```

## Example Playbook

```
- hosts: prometheus
  roles:
    - jcalonso.prometheus-proxy
```

## License

MIT/BSD

## Author Information

Role created in 2019 by [Juan Carlos Alonso](https://jcalonso.com).
