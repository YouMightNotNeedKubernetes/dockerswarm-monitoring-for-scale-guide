> [!WARNING]
> This documentation and stacks are currently a work-in-progress.


# Docker Swarm Monitoring Guide
A documentation on how to get started with Docker Swarm Monitoring

## Stacks
- [grafana](https://github.com/YouMightNotNeedKubernetes/grafana): Docker Stack deployment for Grafana's Dashboard.
- [mimir](https://github.com/YouMightNotNeedKubernetes/mimir): A high-availability Grafana Mimir deployment for Docker Swarm.
- [loki](https://github.com/YouMightNotNeedKubernetes/loki): A high-availability Grafana Loki deployment for Docker Swarm.
- [promstack](https://github.com/YouMightNotNeedKubernetes/promstack): A high-availability prometheus/alertmanager stack for Docker Swarm.
- [promagents](https://github.com/YouMightNotNeedKubernetes/promagents): Docker Stack deployment for cAdvisor & node-exporter.
- [promtail](https://github.com/YouMightNotNeedKubernetes/promtail): Docker Stack deployment for Grafana Loki's Promtail.

## Architecture Overview

<picture>
  <source media="(prefers-color-scheme: dark)" srcset="https://github.com/YouMightNotNeedKubernetes/dockerswarm-monitoring-guide/assets/4363857/507dc46d-0537-45d2-a01a-11c6f57485b2">
  <source media="(prefers-color-scheme: light)" srcset="https://github.com/YouMightNotNeedKubernetes/dockerswarm-monitoring-guide/assets/4363857/b645d44a-c93d-4764-a34f-87cbdb25671e">
  <img alt="Architecture Overview" src="https://github.com/YouMightNotNeedKubernetes/dockerswarm-monitoring-guide/assets/4363857/507dc46d-0537-45d2-a01a-11c6f57485b2">
</picture>

## Getting Started

You will need to create swarm-scoped overlay network called `dockerswarm_monitoring` for all the stacks to communicate.

```sh
$ docker network create --driver overlay --attachable dockerswarm_monitoring
```
