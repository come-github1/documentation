
## Event Categories


The following table lists the data source offered by this integration.

| Data Source | Description                          |
| ----------- | ------------------------------------ |
| `Authentication logs` | Authentication packets are logged |
| `Network device logs` | Network packets are logged by Always On VPN |





In details, the following table denotes the type of events produced by this integration.

| Name | Values |
| ---- | ------ |
| Kind | `event` |
| Category | `network` |
| Type | `` |




## Event Samples

Find below few samples of events and how they are normalized by SEKOIA.IO.


=== "access_accept_event.json"

    ```json
	
    {
        "message": "\"VPNTEST1\",\"RAS\",09/22/2022,13:32:06,2,,\"DOMAIN\\doe-j\",,,,,,,,,,,,,,,1,2,11,\"VPN TEST\",0,\"311 1 <REDACTED> 08/25/2022 03:41:37 317092\",,,,\"Microsoft: Carte \u00e0 puce ou autre certificat\",,,,,\"317093\",,,,,,,,,,,,,,,,,,,,,,,4,2,\"VPN TEST\",1,,,,",
        "event": {
            "kind": "event",
            "category": [
                "network"
            ],
            "type": [
                "allowed"
            ]
        },
        "@timestamp": "2022-09-22T13:32:06.000000Z",
        "observer": {
            "hostname": "VPNTEST1"
        },
        "service": {
            "name": "RAS"
        },
        "rule": {
            "name": "VPN TEST"
        },
        "user": {
            "domain": "DOMAIN",
            "name": "doe-j"
        },
        "network": {
            "protocol": "PPP"
        },
        "windows": {
            "remote_access_server": {
                "authentication": {
                    "type": 11,
                    "name": "PEAP"
                },
                "reason": {
                    "code": 0,
                    "name": "IAS_SUCCESS"
                },
                "class": "311 1 <REDACTED> 08/25/2022 03:41:37 317092",
                "session": {
                    "id": "317093"
                },
                "packet": {
                    "type": 2,
                    "name": "Access-Accept"
                },
                "service": {
                    "type": 2,
                    "name": "Framed"
                },
                "framed_protocol": {
                    "type": 1,
                    "name": "PPP"
                },
                "provider": {
                    "type": 1
                }
            }
        },
        "related": {
            "hosts": [
                "VPNTEST1"
            ],
            "user": [
                "doe-j"
            ]
        }
    }
    	
	```


=== "access_challenge_event.json"

    ```json
	
    {
        "message": "\"VPNTEST1\",\"RAS\",09/22/2022,13:32:06,11,,\"DOMAIN\\doe-j\",,,,,,,,,,,,,,,,,11,\"VPN TEST\",0,\"311 1 <REDACTED> 08/25/2022 03:41:37 317091\",30,,,,,,,,\"317092\",,,,,,,,,,,,,,,,,,,,,,,,,\"VPN TEST\",1,,,,",
        "event": {
            "kind": "event",
            "category": [
                "network"
            ],
            "type": [
                "info"
            ]
        },
        "@timestamp": "2022-09-22T13:32:06.000000Z",
        "observer": {
            "hostname": "VPNTEST1"
        },
        "service": {
            "name": "RAS"
        },
        "rule": {
            "name": "VPN TEST"
        },
        "user": {
            "domain": "DOMAIN",
            "name": "doe-j"
        },
        "windows": {
            "remote_access_server": {
                "authentication": {
                    "type": 11,
                    "name": "PEAP"
                },
                "reason": {
                    "code": 0,
                    "name": "IAS_SUCCESS"
                },
                "class": "311 1 <REDACTED> 08/25/2022 03:41:37 317091",
                "session": {
                    "timeout": 30,
                    "id": "317092"
                },
                "packet": {
                    "type": 11,
                    "name": "Access-Challenge"
                },
                "provider": {
                    "type": 1
                }
            }
        },
        "related": {
            "hosts": [
                "VPNTEST1"
            ],
            "user": [
                "doe-j"
            ]
        }
    }
    	
	```


=== "access_request_event.json"

    ```json
	
    {
        "message": "\"VPNTEST1\",\"RAS\",09/22/2022,13:32:06,1,\"jdoe@mydomain.org\",\"DOMAIN\\doe-j\",\"5.6.7.8\",\"4.3.2.1\",,,\"VPNTEST1\",\"1.2.3.4\",1519,,\"1.2.3.4\",\"VPNTEST1\",,,5,,1,2,11,\"VPN TEST\",0,\"311 1 <REDACTED> 08/25/2022 03:41:37 317092\",,,,\"Microsoft: Carte \u00e0 puce ou autre certificat\",,,,,\"317093\",,,,,,,,,79617,1,\"4.3.2.1\",\"5.6.7.8\",,,,,,,\"MSRASV5.20\",311,,,,,\"VPN TEST\",1,,,\"MSRAS-0-UC11480\",\"MSRASV5.20\"",
        "event": {
            "kind": "event",
            "category": [
                "network"
            ],
            "type": [
                "info"
            ]
        },
        "@timestamp": "2022-09-22T13:32:06.000000Z",
        "observer": {
            "hostname": "VPNTEST1"
        },
        "service": {
            "name": "RAS"
        },
        "user": {
            "email": "jdoe@mydomain.org",
            "domain": "DOMAIN",
            "name": "doe-j"
        },
        "source": {
            "ip": "1.2.3.4",
            "nat": {
                "ip": "4.3.2.1",
                "port": 1519
            },
            "address": "1.2.3.4"
        },
        "rule": {
            "name": "VPN TEST"
        },
        "network": {
            "protocol": "PPP"
        },
        "windows": {
            "remote_access_server": {
                "authentication": {
                    "type": 11,
                    "name": "PEAP"
                },
                "reason": {
                    "code": 0,
                    "name": "IAS_SUCCESS"
                },
                "class": "311 1 <REDACTED> 08/25/2022 03:41:37 317092",
                "session": {
                    "id": "317093"
                },
                "packet": {
                    "type": 1,
                    "name": "Access-Request"
                },
                "service": {
                    "type": 2,
                    "name": "Framed"
                },
                "tunnel_medium": {
                    "type": 1,
                    "name": "IPv4"
                },
                "framed_protocol": {
                    "type": 1,
                    "name": "PPP"
                },
                "provider": {
                    "type": 1
                }
            }
        },
        "related": {
            "hosts": [
                "VPNTEST1"
            ],
            "ip": [
                "1.2.3.4",
                "4.3.2.1"
            ],
            "user": [
                "doe-j"
            ]
        }
    }
    	
	```


=== "accounting_request_event.json"

    ```json
	
    {
        "message": "\"VPNTEST1\",\"RAS\",09/22/2022,13:32:06,4,\"jdoe@mydomain.org\",,\"5.6.7.8\",\"4.3.2.1\",,\"172.16.2.58\",\"VPNTEST1\",\"1.2.3.4\",1519,,\"1.2.3.4\",\"VPNTEST1\",1663846326,,5,,1,2,,,0,\"311 1 <REDACTED> 08/25/2022 03:41:37 317092\",,,,,1,,,,\"317093\",3,,,,,\"50765\",1,,79617,1,\"4.3.2.1\",\"5.6.7.8\",,,,,,,\"MSRASV5.20\",311,,,0,,\"VPN TEST\",,,,\"MSRAS-0-UC11480\",\"MSRASV5.20\"",
        "event": {
            "kind": "event",
            "category": [
                "network"
            ],
            "type": [
                "info"
            ]
        },
        "@timestamp": "2022-09-22T13:32:06.000000Z",
        "observer": {
            "hostname": "VPNTEST1"
        },
        "service": {
            "name": "RAS"
        },
        "user": {
            "email": "jdoe@mydomain.org"
        },
        "source": {
            "ip": "1.2.3.4",
            "nat": {
                "ip": "4.3.2.1",
                "port": 1519
            },
            "address": "1.2.3.4"
        },
        "network": {
            "protocol": "PPP"
        },
        "windows": {
            "remote_access_server": {
                "reason": {
                    "code": 0,
                    "name": "IAS_SUCCESS"
                },
                "class": "311 1 <REDACTED> 08/25/2022 03:41:37 317092",
                "session": {
                    "id": "317093"
                },
                "packet": {
                    "type": 4,
                    "name": "Accounting-Request"
                },
                "service": {
                    "type": 2,
                    "name": "Framed"
                },
                "tunnel_medium": {
                    "type": 1,
                    "name": "IPv4"
                },
                "framed_protocol": {
                    "type": 1,
                    "name": "PPP"
                }
            }
        },
        "related": {
            "hosts": [
                "VPNTEST1"
            ],
            "ip": [
                "1.2.3.4",
                "4.3.2.1"
            ]
        }
    }
    	
	```





## Extracted Fields

The following table lists the fields that are extracted, normalized under the ECS format, analyzed and indexed by the parser. It should be noted that infered fields are not listed.

| Name | Type | Description                |
| ---- | ---- | ---------------------------|
|`@timestamp` | `date` | Date/time when the event originated. |
|`event.category` | `keyword` | Event category. The second categorization field in the hierarchy. |
|`event.kind` | `keyword` | The kind of the event. The highest categorization field in the hierarchy. |
|`observer.hostname` | `keyword` | Hostname of the observer. |
|`rule.name` | `keyword` | Rule name |
|`service.name` | `keyword` | Name of the service. |
|`source.ip` | `ip` | IP address of the source. |
|`source.nat.ip` | `ip` | Source NAT ip |
|`source.nat.port` | `long` | Source NAT port |
|`user.domain` | `keyword` | Name of the directory the user is a member of. |
|`user.email` | `keyword` | User email address. |
|`user.name` | `keyword` | Short name or login of the user. |
|`windows.remote_access_server.authentication.type` | `number` | The code of the authentication scheme |
|`windows.remote_access_server.class` | `keyword` | The attribute sent to the client in a Access-Accept packet |
|`windows.remote_access_server.framed_protocol.type` | `number` | The type of the RADIUS framed protocol |
|`windows.remote_access_server.packet.type` | `number` | The code of the RADIUS packet type |
|`windows.remote_access_server.provider.name` | `keyword` | The name of the authentication provider |
|`windows.remote_access_server.provider.type` | `number` | The code of the authentication provider |
|`windows.remote_access_server.reason.code` | `number` | The code of the authentication status |
|`windows.remote_access_server.service.type` | `number` | The code of the RADIUS service type |
|`windows.remote_access_server.session.id` | `keyword` | The identifier of the session |
|`windows.remote_access_server.session.timeout` | `number` | The timeout of the session |
|`windows.remote_access_server.tunnel_medium.type` | `number` | The code of the RADIUS tunnel medium type |

