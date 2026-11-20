# 👋 Awesome Prometheus Alerts [![Awesome](https://awesome.re/badge-flat.svg)](https://awesome.re)

> **Provenance:** this repository is a copy of [samber/awesome-prometheus-alerts](https://github.com/samber/awesome-prometheus-alerts) (rules, Jekyll site, `LICENSE`), kept as a template for Prometheus alerting rules. All rules and site content are the work of the upstream authors and contributors and are licensed CC BY 4.0 (see [License](#-license)). `_config.yml` still points at the upstream repository. TODO: document any local modifications; the history contains a single commit so none can be identified.

## Prerequisites

- Docker and Docker Compose (to preview the Jekyll site), or Ruby with Bundler (`Gemfile`)
- Node.js (only for `npm test`, which runs `awesome-lint`)
- A Prometheus and Alertmanager setup to load the rules into

## Quick start

Alerting rules are authored in `_data/rules.yml`; generated, ready-to-use Prometheus rule files are under `dist/rules/<technology>/<exporter>.yml`, and `dist/rules/email_template.tmpl` is an Alertmanager email template. Copy the rule files you need into your Prometheus `rule_files` location.

Preview the site locally (serves on `http://localhost:4000`):

```bash
docker-compose up
# or
bundle install && jekyll serve
```

## Repository structure

```
.
├── _data/rules.yml        # source of all rules
├── _layouts/ assets/      # Jekyll theme and static files
├── index.md rules.md alertmanager.md blackbox-exporter.md sleep-peacefully.md   # site pages
├── dist/rules/            # generated rule files per exporter
├── dist/template.yml      # Liquid template used to render rule files
├── CONTRIBUTING.md        # how to add or improve rules
└── LICENSE                # CC BY 4.0
```

> Most alerting rules are common to every Prometheus setup. We need a place to find them all. 🤘 🚨 📊

Collection available here: **[https://samber.github.io/awesome-prometheus-alerts](https://samber.github.io/awesome-prometheus-alerts)**

## ✨ Contents

- [Rules](#-rules)
- [Contributing](#-contributing)
- [Improvements](#-improvements)
- [Help us](#-show-your-support)
- [License](#-license)

## 🚨 Rules

#### Basic resource monitoring

- [Prometheus self-monitoring](https://samber.github.io/awesome-prometheus-alerts/rules#prometheus-internals)
- [Host/Hardware](https://samber.github.io/awesome-prometheus-alerts/rules#host-and-hardware)
- [Docker Containers](https://samber.github.io/awesome-prometheus-alerts/rules#docker-containers)
- [Blackbox](https://samber.github.io/awesome-prometheus-alerts/rules#blackbox)
- [Windows](https://samber.github.io/awesome-prometheus-alerts/rules#windows-server)
- [VMWare](https://samber.github.io/awesome-prometheus-alerts/rules#vmware)
- [Netdata](https://samber.github.io/awesome-prometheus-alerts/rules#netdata)

#### Databases and brokers

- [MySQL](https://samber.github.io/awesome-prometheus-alerts/rules#mysql)
- [PostgreSQL](https://samber.github.io/awesome-prometheus-alerts/rules#postgresql)
- [PGBouncer](https://samber.github.io/awesome-prometheus-alerts/rules#pgbouncer)
- [Redis](https://samber.github.io/awesome-prometheus-alerts/rules#redis)
- [MongoDB](https://samber.github.io/awesome-prometheus-alerts/rules#mongodb)
- [RabbitMQ](https://samber.github.io/awesome-prometheus-alerts/rules#rabbitmq)
- [Elasticsearch](https://samber.github.io/awesome-prometheus-alerts/rules#elasticsearch)
- [Cassandra](https://samber.github.io/awesome-prometheus-alerts/rules#cassandra)
- [Zookeeper](https://samber.github.io/awesome-prometheus-alerts/rules#zookeeper)
- [Kafka](https://samber.github.io/awesome-prometheus-alerts/rules#kafka)
- [Pulsar](https://samber.github.io/awesome-prometheus-alerts/rules#pulsar)
- [Solr](https://samber.github.io/awesome-prometheus-alerts/rules#solr)

#### Reverse proxies and load balancers

- [Nginx](https://samber.github.io/awesome-prometheus-alerts/rules#nginx)
- [Apache](https://samber.github.io/awesome-prometheus-alerts/rules#apache)
- [HaProxy](https://samber.github.io/awesome-prometheus-alerts/rules#haproxy)
- [Traefik](https://samber.github.io/awesome-prometheus-alerts/rules#traefik)

#### Runtimes

- [PHP-FPM](https://samber.github.io/awesome-prometheus-alerts/rules#php-fpm)
- [JVM](https://samber.github.io/awesome-prometheus-alerts/rules#jvm)
- [Sidekiq](https://samber.github.io/awesome-prometheus-alerts/rules#sidekiq)

#### Orchestrators
- [Kubernetes](https://samber.github.io/awesome-prometheus-alerts/rules#kubernetes)
- [Nomad](https://samber.github.io/awesome-prometheus-alerts/rules#nomad)
- [Consul](https://samber.github.io/awesome-prometheus-alerts/rules#consul)
- [Etcd](https://samber.github.io/awesome-prometheus-alerts/rules#etcd)
- [Linkerd](https://samber.github.io/awesome-prometheus-alerts/rules#linkerd)
- [Istio](https://samber.github.io/awesome-prometheus-alerts/rules#istio)
- [ArgoCD](https://samber.github.io/awesome-prometheus-alerts/rules#argocd)

#### Network, security and storage

- [Ceph](https://samber.github.io/awesome-prometheus-alerts/rules#ceph)
- [ZFS](https://samber.github.io/awesome-prometheus-alerts/rules#zfs)
- [OpenEBS](https://samber.github.io/awesome-prometheus-alerts/rules#openebs)
- [Minio](https://samber.github.io/awesome-prometheus-alerts/rules#minio)
- [SSL/TLS](https://samber.github.io/awesome-prometheus-alerts/rules#ssl/tls)
- [Juniper](https://samber.github.io/awesome-prometheus-alerts/rules#juniper)
- [CoreDNS](https://samber.github.io/awesome-prometheus-alerts/rules#coredns)
- [FreeSwitch](https://samber.github.io/awesome-prometheus-alerts/rules#freeswitch)
- [Hashicorp Vault](https://samber.github.io/awesome-prometheus-alerts/rules#hashicorp-vault)
- [Cloudflare](https://samber.github.io/awesome-prometheus-alerts/rules#cloudflare)

#### Other

- [Thanos](https://samber.github.io/awesome-prometheus-alerts/rules#thanos)
- [Loki](https://samber.github.io/awesome-prometheus-alerts/rules#loki)
- [Promtail](https://samber.github.io/awesome-prometheus-alerts/rules#promtail)
- [Cortex](https://samber.github.io/awesome-prometheus-alerts/rules#cortex)
- [Jenkins](https://samber.github.io/awesome-prometheus-alerts/rules#jenkins)

## 🤝 Contributing

Contributions from community (you!) are most welcome!

There are many ways to contribute: writing code, alerting rules, documentation, reporting issues, discussing better error tracking...

[Instructions here](CONTRIBUTING.md)

## 🏋️ Improvements

- Create an alert rule builder in Jekyll for custom alerts (severity, thresholds, instances...)
- Add resolution suggestions to rule descriptions, for faster incident resolution ([#85](https://github.com/samber/awesome-prometheus-alerts/issues/85)).

## 👏 Thanks

Gratitude for the Gitlab operation team that provided 50+ rules. \o/

## 📜 License

[Creative Commons Attribution 4.0 International License (CC BY 4.0)](LICENSE), (c) the awesome-prometheus-alerts authors. Original work: https://github.com/samber/awesome-prometheus-alerts

## Author

Template repository maintained by Umesh Khatiwada - https://github.com/umesh-khatiwada
