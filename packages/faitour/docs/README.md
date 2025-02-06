# Faitour

This integration is for [Faitour](https://github.com/MakoWish/Faitour) honeypot event logs. The package processes messages from Faitour honeypot logs.

## Data streams

The Faitour integration collects the following event types:

- **events**

## Requirements

Elastic Agent must be installed. For more details and installation instructions, please refer to the [Elastic Agent Installation Guide](https://www.elastic.co/guide/en/fleet/current/elastic-agent-installation.html).

### Installing and managing an Elastic Agent:

There are several options for installing and managing Elastic Agent:

### Install a Fleet-managed Elastic Agent (recommended):

With this approach, you install Elastic Agent and use Fleet in Kibana to define, configure, and manage your agents in a central location. We recommend using Fleet management because it makes the management and upgrade of your agents considerably easier.

### Install Elastic Agent in standalone mode (advanced users):

With this approach, you install Elastic Agent and manually configure the agent locally on the system where it’s installed. You are responsible for managing and upgrading the agents. This approach is reserved for advanced users only.

### Install Elastic Agent in a containerized environment:

You can run Elastic Agent inside a container, either with Fleet Server or standalone. Docker images for all versions of Elastic Agent are available from the Elastic Docker registry, and we provide deployment manifests for running on Kubernetes.

Please note, there are minimum requirements for running Elastic Agent. For more information, refer to the  [Elastic Agent Minimum Requirements](https://www.elastic.co/guide/en/fleet/current/elastic-agent-installation.html#elastic-agent-installation-minimum-requirements).


### Enabling the integration in Elastic:

1. In Kibana navigate to Management > Integrations.
2. In "Search for integrations" top bar, search for `Faitour`.
3. Select the "Faitour" integration from the search results.
4. Select "Add Faitour" to add the integration.
5. Add all the required integration configuration parameters.
6. Select "Save and continue" to save the integration.

## Logs

### Faitour

The `events` dataset collects the Faitour honeypot logs.

An example event for `events` looks as following:

```json
{
    "agent": {
        "name": "Faitour1",
        "id": "4c2a0bd3-d983-4b59-9cf8-36ff05b4d06a",
        "ephemeral_id": "0f54b936-9dc4-4b7f-8dfa-0d9b95043218",
        "type": "filebeat",
        "version": "8.16.3"
    },
    "log": {
        "level": "INFO",
        "logger": "faitour",
        "origin": {
            "file": {
                "line": "72",
                "name": "/opt/Faitour2/emulators/http.py"
            }
        }
    },
    "elastic_agent": {
        "id": "4c2a0bd3-d983-4b59-9cf8-36ff05b4d06a",
        "version": "8.16.3",
        "snapshot": false
    },
    "destination": {
        "port": 80,
        "ip": "10.10.10.10"
    },
    "source": {
        "geo": {
            "continent_name": "North America",
            "region_iso_code": "CA",
            "city_name": "Los Angeles",
            "country_iso_code": "US",
            "timezone": "America/Los_Angeles",
            "country_name": "United States",
            "continent_code": "NA",
            "location": {
                "lon": "-117.853",
                "lat": "33.931"
            },
            "region_name": "California",
            "postal_code": 90202
        },
        "registered_domain": "contoso.com",
        "port": 59607,
        "top_level_domain": "com",
        "ip": "89.160.20.114",
        "domain": "web.contoso.com",
        "subdomain": "web"
    },
    "url": {
        "path": "/api/cluster",
        "original": "http://faitour1.contoso.com/api/cluster",
        "scheme": "http",
        "domain": "faitour1.contoso.com"
    },
    "input": {
        "type": "log"
    },
    "@timestamp": "2025-02-04T11:02:36.113Z",
    "ecs": {
        "version": "8.0.0"
    },
    "related": {
        "hosts": [
            "FAITOUR1"
        ],
        "ip": [
            "10.10.10.10",
            "fe80::250:56ff:fea9:3c08",
            "89.160.20.114"
        ],
        "domain": [
            "AmersnmidD-prd1.appliedmed.com"
        ]
    },
    "data_stream": {
        "namespace": "default",
        "type": "logs",
        "dataset": "faitour.log"
    },
    "host": {
        "hostname": "Faitour1",
        "os": {
            "kernel": "6.8.0-52-generic",
            "codename": "noble",
            "name": "Ubuntu",
            "type": "linux",
            "family": "debian",
            "version": "24.04.1 LTS (Noble Numbat)",
            "platform": "ubuntu"
        },
        "containerized": false,
        "ip": [
            "10.10.10.10",
            "fe80::250:56ff:d981:a7cf"
        ],
        "name": "FAITOUR1",
        "id": "1249880f0cd14c3a8845afbeb55adf8d",
        "mac": [
            "00-11-22-33-44-55"
        ],
        "architecture": "x86_64"
    },
    "http": {
        "request": {
            "method": "GET"
        },
        "response": {
            "status_code": 404
        }
    },
    "event": {
        "agent_id_status": "verified",
        "reason": "HTTP GET Request",
        "ingested": "2025-02-04T11:03:02Z",
        "kind": "alert",
        "module": "http",
        "action": "http_get",
        "type": [
            "connection",
            "denied",
            "start"
        ],
        "category": [
            "network",
            "intrusion_detection"
        ],
        "dataset": "honeypot",
        "outcome": "failure"
    },
    "timestamp": "2025-02-04T11:02:35.193Z"
}
```

**Exported fields**

| Field | Description | Type |
|---|---|---|
| @timestamp | Date/time when the event originated. This is the date/time extracted from the event, typically representing when the event was generated by the source. If the event source has no original timestamp, this value is typically populated by the first time the event was received by the pipeline. Required field for all events. | date |
| cloud.image.id | Image ID for the cloud instance. | keyword |
| data_stream.dataset | Data stream dataset. | constant_keyword |
| data_stream.namespace | Data stream namespace. | constant_keyword |
| data_stream.type | Data stream type. | constant_keyword |
| event.dataset | Event dataset | constant_keyword |
| event.module | Event module | constant_keyword |
| host.containerized | If the host is a container. | boolean |
| host.os.build | OS build information. | keyword |
| host.os.codename | OS codename, if any. | keyword |
| input.type | Input type. | keyword |
| log.offset | Offset of the entry in the log file. | long |

