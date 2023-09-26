# Proxmox VE

## Overview

The [Proxmox VE](https://www.proxmox.com/en/) integration allows users to monitor activity, resources, and tasks. Proxmox delivers powerful, enterprise-grade solutions with full access to all functionality for everyone - highly reliable and secure. The software-defined and open platforms are easy to deploy, manage and budget for.

Use the Proxmox VE integration to collect and parse data from the REST APIs. Then visualize that data in Kibana.

## Data streams

The Proxmox VE integration collects logs for three types of events: Log, Resources, Tasks.

**Log** is used to get details related to events that occur on the Proxmox VE host. See more details in the API documentation [here](https://pve.proxmox.com/pve-docs/api-viewer/#/cluster/log).

**Resources** is used to host resource usage details. See more details in the API documentation [here](https://pve.proxmox.com/pve-docs/api-viewer/#/cluster/resources).

**Tasks** is used to retrieve the state of tasks run on the host. See more details in the API documentation [here](https://pve.proxmox.com/pve-docs/api-viewer/#/cluster/tasks).

## Compatibility

This module has been tested against `Proxmox VE 8.0` [Last Updated 22 June 2023](https://www.proxmox.com/en/downloads/proxmox-virtual-environment/iso/proxmox-ve-8-0-iso-installer).

## Requirements

Elasticsearch is needed to store and search data, and Kibana is needed for visualizing and managing it. You can use our hosted Elasticsearch Service on Elastic Cloud, which is recommended, or self-manage the Elastic Stack on your hardware.

## Setup

### To collect data from the Proxmox VE REST APIs, follow the steps outlined in the [Proxmox VE API Documentation](https://pve.proxmox.com/wiki/Proxmox_VE_API).

## Logs reference

### Proxmox VE Log

The `log` dataset collects the Proxmox VE activity logs.

#### Example

{{event "log"}}

{{fields "log"}}

### Proxmox VE Resources

The `resources` dataset collects the Proxmox VE system resources.

#### Example

{{event "resources"}}

{{fields "resources"}}

### Proxmox VE Tasks

The `tasks` dataset collects the Proxmox VE task logs.

#### Example

{{event "tasks"}}

{{fields "tasks"}}
