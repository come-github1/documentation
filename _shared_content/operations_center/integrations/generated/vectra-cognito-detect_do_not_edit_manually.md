
## Event Categories


The following table lists the data source offered by this integration.

| Data Source | Description                          |
| ----------- | ------------------------------------ |
| `Authentication logs` | Audit logs are generated for login events,logout events, as well as other user actions that can impact the security posture of the product. |








## Event Samples

Find below few samples of events and how they are normalized by SEKOIA.IO.


=== "vectra_account_scoring.json"

    ```json
	
    {
        "message": "- :{\"version\":\"6.12\",\"account_id\":123456,\"headend_addr\":\"198.51.100.94\",\"account_uid\":\"admin-prtg@company.local\",\"threat\":0,\"certainty\":0,\"score_decreases\":true,\"privilege\":4,\"href\":\"https:/198.51.100.94/accounts/522\",\"category\":\"ACCOUNT SCORING\",\"tags\":[],\"host_access_history\":[{\"id\":22235,\"name\":\"HOSTNAME.COMPANY.LOCAL\",\"privilege\":null,\"privilegeCategory\":null,\"lastSeen\":\"2021-09-30T08:06:46+00:00\"}],\"service_access_history\":[{\"id\":1470943,\"uid\":\"cifs/serssq01.company.local@company.local\",\"privilege\":4,\"privilegeCategory\":\"Medium\",\"lastSeen\":\"2021-09-30T08:06:46+00:00\"},{\"id\":5,\"uid\":\"krbtgt/company.local.company@company\",\"privilege\":null,\"privilegeCategory\":null,\"lastSeen\":\"2021-09-30T08:04:19+00:00\"},{\"id\":2614295,\"uid\":\"rpcss/host109.company.local@company.local\",\"privilege\":4,\"privilegeCategory\":\"Medium\",\"lastSeen\":\"2021-09-30T08:04:19+00:00\"},{\"id\":2614304,\"uid\":\"rpcss/host2db01.company.local@company.local\",\"privilege\":4,\"privilegeCategory\":\"Medium\",\"lastSeen\":\"2021-09-30T08:04:04+00:00\"},{\"id\":2614297,\"uid\":\"rpcss/host110.company.local@company.local\",\"privilege\":4,\"privilegeCategory\":\"Medium\",\"lastSeen\":\"2021-09-30T07:57:44+00:00\"},{\"id\":990,\"uid\":\"rpcss/srv-appli02.company.local@company.local\",\"privilege\":4,\"privilegeCategory\":\"Medium\",\"lastSeen\":\"2021-09-30T07:54:04+00:00\"},{\"id\":2614303,\"uid\":\"rpcss/host201.company.local@company.local\",\"privilege\":4,\"privilegeCategory\":\"Medium\",\"lastSeen\":\"2021-09-30T07:37:28+00:00\"},{\"id\":4214403,\"uid\":\"http/alm.company.local@company.local\",\"privilege\":4,\"privilegeCategory\":\"Medium\",\"lastSeen\":\"2021-09-30T07:21:04+00:00\"},{\"id\":4186134,\"uid\":\"http/host109.company.local@company.local\",\"privilege\":4,\"privilegeCategory\":\"Medium\",\"lastSeen\":\"2021-09-30T07:20:50+00:00\"},{\"id\":3693289,\"uid\":\"http/host110.company.local@company.local\",\"privilege\":4,\"privilegeCategory\":\"Medium\",\"lastSeen\":\"2021-09-30T07:20:38+00:00\"}],\"last_detection_type\":\"Privilege Anomaly: Unusual Service - Insider\",\"vectra_timestamp\":\"1633338457\"}",
        "event": {
            "action": "ACCOUNT SCORING",
            "url": "https:/198.51.100.94/accounts/522"
        },
        "observer": {
            "version": "6.12",
            "ip": "198.51.100.94"
        },
        "vectra": {
            "timestamp": 1633338457,
            "account": {
                "id": 123456,
                "uid": "admin-prtg@company.local"
            },
            "certainty": 0,
            "user": {
                "privilege": 4
            },
            "detection": {
                "score_decreases": true,
                "tags": [],
                "last_type": "Privilege Anomaly: Unusual Service - Insider"
            },
            "risk_score_norm": 0,
            "history": {
                "host_access": [
                    {
                        "id": 22235,
                        "name": "HOSTNAME.COMPANY.LOCAL",
                        "privilege": null,
                        "privilegeCategory": null,
                        "lastSeen": "2021-09-30T08:06:46+00:00"
                    }
                ],
                "host_access_hostname": [
                    "HOSTNAME.COMPANY.LOCAL"
                ],
                "service_access": [
                    {
                        "id": 1470943,
                        "uid": "cifs/serssq01.company.local@company.local",
                        "privilege": 4,
                        "privilegeCategory": "Medium",
                        "lastSeen": "2021-09-30T08:06:46+00:00"
                    },
                    {
                        "id": 5,
                        "uid": "krbtgt/company.local.company@company",
                        "privilege": null,
                        "privilegeCategory": null,
                        "lastSeen": "2021-09-30T08:04:19+00:00"
                    },
                    {
                        "id": 2614295,
                        "uid": "rpcss/host109.company.local@company.local",
                        "privilege": 4,
                        "privilegeCategory": "Medium",
                        "lastSeen": "2021-09-30T08:04:19+00:00"
                    },
                    {
                        "id": 2614304,
                        "uid": "rpcss/host2db01.company.local@company.local",
                        "privilege": 4,
                        "privilegeCategory": "Medium",
                        "lastSeen": "2021-09-30T08:04:04+00:00"
                    },
                    {
                        "id": 2614297,
                        "uid": "rpcss/host110.company.local@company.local",
                        "privilege": 4,
                        "privilegeCategory": "Medium",
                        "lastSeen": "2021-09-30T07:57:44+00:00"
                    },
                    {
                        "id": 990,
                        "uid": "rpcss/srv-appli02.company.local@company.local",
                        "privilege": 4,
                        "privilegeCategory": "Medium",
                        "lastSeen": "2021-09-30T07:54:04+00:00"
                    },
                    {
                        "id": 2614303,
                        "uid": "rpcss/host201.company.local@company.local",
                        "privilege": 4,
                        "privilegeCategory": "Medium",
                        "lastSeen": "2021-09-30T07:37:28+00:00"
                    },
                    {
                        "id": 4214403,
                        "uid": "http/alm.company.local@company.local",
                        "privilege": 4,
                        "privilegeCategory": "Medium",
                        "lastSeen": "2021-09-30T07:21:04+00:00"
                    },
                    {
                        "id": 4186134,
                        "uid": "http/host109.company.local@company.local",
                        "privilege": 4,
                        "privilegeCategory": "Medium",
                        "lastSeen": "2021-09-30T07:20:50+00:00"
                    },
                    {
                        "id": 3693289,
                        "uid": "http/host110.company.local@company.local",
                        "privilege": 4,
                        "privilegeCategory": "Medium",
                        "lastSeen": "2021-09-30T07:20:38+00:00"
                    }
                ],
                "service_access_uid": {
                    "host": [
                        "serssq01.company.local@company.local",
                        "company.local.company@company",
                        "host109.company.local@company.local",
                        "host2db01.company.local@company.local",
                        "host110.company.local@company.local",
                        "srv-appli02.company.local@company.local",
                        "host201.company.local@company.local",
                        "alm.company.local@company.local",
                        "host109.company.local@company.local",
                        "host110.company.local@company.local"
                    ],
                    "proto_host": [
                        "cifs/serssq01.company.local@company.local",
                        "krbtgt/company.local.company@company",
                        "rpcss/host109.company.local@company.local",
                        "rpcss/host2db01.company.local@company.local",
                        "rpcss/host110.company.local@company.local",
                        "rpcss/srv-appli02.company.local@company.local",
                        "rpcss/host201.company.local@company.local",
                        "http/alm.company.local@company.local",
                        "http/host109.company.local@company.local",
                        "http/host110.company.local@company.local"
                    ]
                }
            }
        },
        "related": {
            "ip": [
                "198.51.100.94"
            ]
        }
    }
    	
	```


=== "vectra_campaign.json"

    ```json
	
    {
        "message": "-: {\"src_name\": \"IP-255.255.255.1\", \"src_ip\": \"255.255.255.1\", \"src_hid\": 11111, \"dest_name\": \"push.services.mozilla.com\", \"dest_ip\": \"255.255.255.2\", \"dest_id\": \"external\", \"timestamp\": 1111111222.0, \"campaign_name\": \"push.services.mozilla.com-13\", \"campaign_id\": 222, \"campaign_link\": \"https://255.255.255.3/campaigns/222\", \"action\": \"ADD\", \"reason\": \"Connection\", \"version\": \"6.8\", \"headend_addr\": \"255.255.255.3\", \"dvchost\": \"255.255.255.3\", \"vectra_timestamp\": \"1111111111\"}",
        "observer": {
            "version": "6.8",
            "name": "255.255.255.3",
            "ip": "255.255.255.3"
        },
        "vectra": {
            "timestamp": 1111111111,
            "campaign": {
                "id": 222,
                "link": "https://255.255.255.3/campaigns/222",
                "name": "push.services.mozilla.com-13"
            },
            "destination": {
                "id": "external",
                "name": "push.services.mozilla.com"
            },
            "detection": {
                "reason": "Connection"
            },
            "source": {
                "hid": 11111,
                "name": "IP-255.255.255.1"
            }
        },
        "action": {
            "name": "ADD"
        },
        "destination": {
            "ip": "255.255.255.2",
            "address": "255.255.255.2"
        },
        "source": {
            "ip": "255.255.255.1",
            "address": "255.255.255.1"
        },
        "related": {
            "ip": [
                "255.255.255.1",
                "255.255.255.2",
                "255.255.255.3"
            ]
        }
    }
    	
	```


=== "vectra_command_control.json"

    ```json
	
    {
        "message": "-: {\"version\": \"6.12\", \"detection_id\": 13281, \"category\": \"COMMAND & CONTROL\", \"severity\": 6.0, \"threat\": 60, \"certainty\": 72, \"d_type\": \"hidden_http_tunnel_cnc\", \"d_type_vname\": \"Hidden HTTP Tunnel\", \"triaged\": false, \"headend_addr\": \"198.51.100.94\", \"dvchost\": \"198.51.100.94\", \"href\": \"https://198.51.100.94/detections/13281?detail_id=94738\", \"dd_dst_ip\": \"198.51.100.1\", \"dd_dst_port\": 8002, \"dd_dst_dns\": \"mirror.centos.org\", \"dd_bytes_sent\": 1476677, \"dd_bytes_rcvd\": 8269214038, \"host_name\": \"IP-198.51.100.14\", \"host_ip\": \"198.51.100.14\", \"dd_proto\": \"tcp\", \"vectra_timestamp\": \"1633516306\"}",
        "event": {
            "action": "COMMAND & CONTROL",
            "url": "https://198.51.100.94/detections/13281?detail_id=94738"
        },
        "observer": {
            "version": "6.12",
            "name": "198.51.100.94",
            "ip": "198.51.100.94"
        },
        "vectra": {
            "timestamp": 1633516306,
            "certainty": 72,
            "detection": {
                "type": "hidden_http_tunnel_cnc",
                "name": "Hidden HTTP Tunnel",
                "id": 13281
            },
            "severity": 6.0,
            "risk_score_norm": 60,
            "triaged": false
        },
        "source": {
            "bytes": 1476677
        },
        "destination": {
            "bytes": 8269214038,
            "domain": "mirror.centos.org",
            "ip": "198.51.100.1",
            "port": 8002,
            "address": "mirror.centos.org",
            "top_level_domain": "org",
            "subdomain": "mirror",
            "registered_domain": "centos.org"
        },
        "network": {
            "protocol": "tcp"
        },
        "host": {
            "ip": [
                "198.51.100.14"
            ],
            "name": "IP-198.51.100.14"
        },
        "related": {
            "ip": [
                "198.51.100.1",
                "198.51.100.14",
                "198.51.100.94"
            ],
            "hosts": [
                "mirror.centos.org"
            ]
        }
    }
    	
	```


=== "vectra_host_scoring.json"

    ```json
	
    {
        "message": "-: {\"version\": \"6.12\", \"host_id\": 27617, \"headend_addr\": \"198.51.100.94\", \"host_name\": \"IP-198.51.100.14\", \"dvchost\": \"198.51.100.94\", \"host_ip\": \"198.51.100.14\", \"threat\": 22, \"certainty\": 31, \"privilege\": 0, \"score_decreases\": false, \"href\": \"https://198.51.100.94/hosts/27617\", \"host_roles\": \"\", \"src_key_asset\": false, \"dst_key_asset\": false, \"category\": \"HOST SCORING\", \"sensor\": \"E123456789123456\", \"detection_profile\": {\"name\": \"saas\", \"vname\": \"Cloud Services\", \"scoringDetections\": [\"Hidden HTTP Tunnel (C&C)\"]}, \"host_groups\": [], \"tags\": [], \"account_access_history\": [], \"service_access_history\": [], \"mac_address\": null, \"mac_vendor\": null, \"last_detection_type\": \"Hidden HTTP Tunnel\", \"vectra_timestamp\": \"1633690973\"}",
        "event": {
            "action": "HOST SCORING",
            "url": "https://198.51.100.94/hosts/27617"
        },
        "observer": {
            "version": "6.12",
            "name": "198.51.100.94",
            "ip": "198.51.100.94",
            "product": "E123456789123456"
        },
        "vectra": {
            "timestamp": 1633690973,
            "history": {
                "account_access": [],
                "service_access": []
            },
            "destination": {
                "key_asset": false
            },
            "user": {
                "privilege": 0
            },
            "detection": {
                "profile": {
                    "name": "saas",
                    "vname": "Cloud Services",
                    "scoringDetections": [
                        "Hidden HTTP Tunnel (C&C)"
                    ]
                },
                "score_decreases": false,
                "tags": [],
                "last_type": "Hidden HTTP Tunnel"
            },
            "certainty": 31,
            "source": {
                "key_asset": false
            },
            "risk_score_norm": 22,
            "host": {
                "group": []
            }
        },
        "host": {
            "id": "27617",
            "ip": [
                "198.51.100.14"
            ],
            "name": "IP-198.51.100.14"
        },
        "related": {
            "ip": [
                "198.51.100.14",
                "198.51.100.94"
            ]
        }
    }
    	
	```


=== "vectra_info.json"

    ```json
	
    {
        "message": "-: {\"category\": \"INFO\", \"certainty\": 0, \"d_type\": \"si_new_host\", \"d_type_vname\": \"New Host\", \"dd_bytes_rcvd\": null, \"dd_bytes_sent\": null, \"dd_dst_dns\": \"\", \"dd_dst_ip\": \"0.0.0.0\", \"dd_dst_port\": 80, \"dd_proto\": \"\", \"detection_id\": 9999, \"dvchost\": \"255.255.255.1\", \"headend_addr\": \"255.255.255.1\", \"host_ip\": \"10.0.0.1\", \"host_name\": \"plop-99\", \"href\": \"https://255.255.255.1/detections/9999?detail_id=11111\", \"severity\": 0, \"threat\": 0, \"triaged\": false, \"vectra_timestamp\": \"1099999999\", \"version\": \"6.7\"}",
        "event": {
            "action": "INFO",
            "url": "https://255.255.255.1/detections/9999?detail_id=11111"
        },
        "observer": {
            "version": "6.7",
            "name": "255.255.255.1",
            "ip": "255.255.255.1"
        },
        "vectra": {
            "timestamp": 1099999999,
            "certainty": 0,
            "detection": {
                "type": "si_new_host",
                "name": "New Host",
                "id": 9999
            },
            "severity": 0,
            "risk_score_norm": 0,
            "triaged": false
        },
        "destination": {
            "ip": "0.0.0.0",
            "port": 80,
            "address": "0.0.0.0"
        },
        "host": {
            "ip": [
                "10.0.0.1"
            ],
            "name": "plop-99"
        },
        "related": {
            "ip": [
                "0.0.0.0",
                "10.0.0.1",
                "255.255.255.1"
            ]
        }
    }
    	
	```


=== "vectra_lateral_movement.json"

    ```json
	
    {
        "message": "-: {\"accounts\": \"user@company.net\", \"shares\": \"\", \"reason\": \"MORE_PROCESSING_REQUIRED\", \"count\": 295, \"version\": \"6.12\", \"detection_id\": 13295, \"category\": \"LATERAL MOVEMENT\", \"severity\": 2.0, \"threat\": 20, \"certainty\": 74, \"d_type\": \"smb_brute_force\", \"d_type_vname\": \"SMB Brute-Force\", \"triaged\": false, \"headend_addr\": \"198.51.100.94\", \"dvchost\": \"198.51.100.94\", \"href\": \"https://198.51.100.94/detections/13295?detail_id=94908\", \"dd_dst_ip\": \"198.51.100.38\", \"dd_dst_port\": 445, \"dd_dst_dns\": \"\", \"dd_bytes_sent\": null, \"dd_bytes_rcvd\": null, \"host_name\": \"hostname\", \"host_ip\": \"198.51.100.155\", \"dd_proto\": \"\", \"vectra_timestamp\": \"1633681756\"}",
        "event": {
            "action": "LATERAL MOVEMENT",
            "url": "https://198.51.100.94/detections/13295?detail_id=94908"
        },
        "observer": {
            "version": "6.12",
            "name": "198.51.100.94",
            "ip": "198.51.100.94"
        },
        "vectra": {
            "timestamp": 1633681756,
            "certainty": 74,
            "detection": {
                "type": "smb_brute_force",
                "name": "SMB Brute-Force",
                "id": 13295,
                "count": "295",
                "reason": "MORE_PROCESSING_REQUIRED",
                "accounts": "user@company.net"
            },
            "severity": 2.0,
            "risk_score_norm": 20,
            "triaged": false
        },
        "destination": {
            "ip": "198.51.100.38",
            "port": 445,
            "address": "198.51.100.38"
        },
        "host": {
            "ip": [
                "198.51.100.155"
            ],
            "name": "hostname"
        },
        "related": {
            "ip": [
                "198.51.100.155",
                "198.51.100.38",
                "198.51.100.94"
            ]
        }
    }
    	
	```


=== "vectra_threat1.json"

    ```json
	
    {
        "message": "-: {\"version\": \"6.8\", \"detection_id\": 1900, \"category\": \"RECONNAISSANCE\", \"severity\": 7.0, \"threat\": 70, \"certainty\": 86, \"d_type\": \"rpc_recon_1to1\", \"d_type_vname\": \"RPC Targeted Recon\", \"triaged\": false, \"headend_addr\": \"255.255.255.1\", \"dvchost\": \"255.255.255.1\", \"href\": \"https://255.255.255.1/detections/1900?detail_id=66777\", \"dd_dst_ip\": \"10.43.0.81\", \"dd_dst_port\": 49668, \"dd_dst_dns\": \"\", \"dd_bytes_sent\": null, \"dd_bytes_rcvd\": null, \"host_name\": \"IP-192.168.71.1\", \"host_ip\": \"192.168.71.1\", \"dd_proto\": \"\", \"vectra_timestamp\": \"1623742534\"}",
        "event": {
            "action": "RECONNAISSANCE",
            "url": "https://255.255.255.1/detections/1900?detail_id=66777"
        },
        "observer": {
            "version": "6.8",
            "name": "255.255.255.1",
            "ip": "255.255.255.1"
        },
        "vectra": {
            "timestamp": 1623742534,
            "certainty": 86,
            "detection": {
                "type": "rpc_recon_1to1",
                "name": "RPC Targeted Recon",
                "id": 1900
            },
            "severity": 7.0,
            "risk_score_norm": 70,
            "triaged": false
        },
        "destination": {
            "ip": "10.43.0.81",
            "port": 49668,
            "address": "10.43.0.81"
        },
        "host": {
            "ip": [
                "192.168.71.1"
            ],
            "name": "IP-192.168.71.1"
        },
        "related": {
            "ip": [
                "10.43.0.81",
                "192.168.71.1",
                "255.255.255.1"
            ]
        }
    }
    	
	```





## Extracted Fields

The following table lists the fields that are extracted, normalized under the ECS format, analyzed and indexed by the parser. It should be noted that infered fields are not listed.

| Name | Type | Description                |
| ---- | ---- | ---------------------------|
|`destination.bytes` | `long` | Bytes sent from the destination to the source. |
|`destination.domain` | `keyword` | The domain name of the destination. |
|`destination.ip` | `ip` | IP address of the destination. |
|`destination.port` | `long` | Port of the destination. |
|`event.action` | `keyword` | The action captured by the event. |
|`event.outcome` | `keyword` | The outcome of the event. The lowest level categorization field in the hierarchy. |
|`event.url` | `keyword` | Event investigation URL |
|`host.id` | `keyword` | Unique host id. |
|`host.ip` | `ip` | Host ip addresses. |
|`host.mac` | `keyword` | Host MAC addresses. |
|`host.name` | `keyword` | Name of the host. |
|`network.protocol` | `keyword` | Application protocol name. |
|`observer.ip` | `ip` | IP addresses of the observer. |
|`observer.name` | `keyword` | Custom name of the observer. |
|`observer.product` | `keyword` | The product name of the observer. |
|`observer.version` | `keyword` | Observer version. |
|`source.bytes` | `long` | Bytes sent from the source to the destination. |
|`source.ip` | `ip` | IP address of the source. |
|`user.name` | `keyword` | Short name or login of the user. |
|`vectra.account.id` | `long` | The ID of the account |
|`vectra.account.name` | `keyword` | The account name. |
|`vectra.account.uid` | `keyword` | The user ID of the account |
|`vectra.audit.message` | `text` | A message explains the cause/nature of the log |
|`vectra.campaign.id` | `long` | The id of the campaign |
|`vectra.campaign.link` | `keyword` | The link to the campaign in the UI |
|`vectra.campaign.name` | `keyword` | The name of the campaign |
|`vectra.certainty` | `long` | The certainty of the score assigned to this host |
|`vectra.destination.id` | `keyword` | The destination of the campaign. Defaults to 'external' |
|`vectra.destination.key_asset` | `bool` | Whether there is a detection that is targeting this host and this host is a key asset. |
|`vectra.destination.name` | `keyword` | The external domain of the campaign destination |
|`vectra.detection.account` | `keyword` | The related user account. |
|`vectra.detection.accounts` | `keyword` | The related accounts. |
|`vectra.detection.base_object` | `keyword` | The base distinguished name. |
|`vectra.detection.bytes_received` | `keyword` | The bytes of data received. |
|`vectra.detection.bytes_sent` | `keyword` | The bytes of data sent. |
|`vectra.detection.client_name` | `keyword` | The RDP client name. |
|`vectra.detection.client_token` | `keyword` | The RDP client token. |
|`vectra.detection.cookie` | `keyword` | The RDP client token. |
|`vectra.detection.count` | `keyword` | The number of attempts |
|`vectra.detection.dos_type` | `keyword` | The DOS type. |
|`vectra.detection.dst_ips` | `keyword` | The target subnets. |
|`vectra.detection.extensions` | `keyword` | File extensions used. |
|`vectra.detection.function` | `keyword` | The executed function. |
|`vectra.detection.host` | `keyword` | The suspicous host. |
|`vectra.detection.http_method` | `keyword` | The HTTP method. |
|`vectra.detection.http_segment` | `keyword` | The HTTP segment. |
|`vectra.detection.id` | `long` | The detection profile associated with this host. |
|`vectra.detection.ip` | `keyword` | The keywordernal target host. |
|`vectra.detection.keyboard_id` | `keyword` | They keyboard layout ID. |
|`vectra.detection.keyboard_name` | `keyword` | They keyboard layout name. |
|`vectra.detection.last_type` | `keyword` | The most recent type of detection associated with this host. |
|`vectra.detection.matched_domain` | `keyword` | The matched domain. |
|`vectra.detection.matched_ip` | `keyword` | The matched IP. |
|`vectra.detection.matched_user_agent` | `keyword` | The matched user-agent. |
|`vectra.detection.name` | `keyword` | The name of the detection |
|`vectra.detection.namedpipe` | `keyword` | The named pipe. |
|`vectra.detection.networks` | `keyword` | The target subnets. |
|`vectra.detection.normal_admins` | `The normal admins observed.` | keyword |
|`vectra.detection.normal_servers` | `keyword` | The normal servers observed. |
|`vectra.detection.num_attempts` | `keyword` | The number of attempts |
|`vectra.detection.port` | `keyword` | The external port used. |
|`vectra.detection.ports` | `long` | Ports scanned. |
|`vectra.detection.product_id` | `keyword` | The unusual product ID. |
|`vectra.detection.profile` | `object` | The detection profile associated with this host. |
|`vectra.detection.protocol` | `keyword` | The external protocol used. |
|`vectra.detection.ransom_notes` | `keyword` | Ransome notes found. |
|`vectra.detection.reason` | `keyword` | The event name of the campaign or The reason this is suspicious or The error code or The indicating reason. |
|`vectra.detection.received_normal_pattern` | `keyword` | Example received normal pattern. |
|`vectra.detection.received_pattern` | `keyword` | The received pattern. |
|`vectra.detection.referer` | `keyword` | The referer. |
|`vectra.detection.reply_cache_control` | `keyword` | The replay cache control setting. |
|`vectra.detection.request` | `keyword` | The LDAP request. |
|`vectra.detection.response_code` | `keyword` | The response code. |
|`vectra.detection.scans` | `keyword` | The number of attempts. |
|`vectra.detection.score_decreases` | `boolean` | Indicates whether both Threat and Certakeywordy scores are decreasing. |
|`vectra.detection.sent_normal_pattern` | `keyword` | Example sent normal pattern. |
|`vectra.detection.sent_pattern` | `keyword` | The sent pattern. |
|`vectra.detection.shares` | `keyword` | The related files shares. |
|`vectra.detection.sql_fragment` | `keyword` | The SQL fragment. |
|`vectra.detection.successes` | `keyword` | The number of successes. |
|`vectra.detection.tags` | `array` | A text of tags applied to the host. |
|`vectra.detection.threat_feeds` | `keyword` | The name of the threat feed. |
|`vectra.detection.tunnel_type` | `keyword` | The type of hidden tunnel. |
|`vectra.detection.type` | `keyword` | keyword |
|`vectra.detection.url` | `keyword` | The suspicous URL. |
|`vectra.detection.uuid` | `keyword` | The RPC UUID. |
|`vectra.health.message` | `text` | A message explains the cause/nature of the log |
|`vectra.history.account_access` | `array` | The account access history associated with this host. |
|`vectra.history.host_access` | `object` | The host access history associated with this account. |
|`vectra.history.host_access_hostname` | `keyword` | The host access history associated with this account (hostname). |
|`vectra.history.service_access` | `array` | The service access history associated with this host. |
|`vectra.history.service_access_uid.host` | `keyword` | The service access history associated with this account (hostname). |
|`vectra.history.service_access_uid.proto_host` | `keyword` | The service access history associated with this account (protocol + hostname). |
|`vectra.host.group` | `keyword` | To be defined |
|`vectra.host.vendor` | `keyword` | The vendor of the MAC address of this host. |
|`vectra.lockdown.retry` | `boolean` | When a Lockdown action has failed, this indicates whether the system will retry the action. |
|`vectra.risk_score_norm` | `long` | Newly calculated account threat |
|`vectra.severity` | `long` | A score proportional to threat |
|`vectra.source.hid` | `long` | The original host ID of the member host in this campaign |
|`vectra.source.key_asset` | `boolean` | Whether the host being scored is marked as a key asset |
|`vectra.source.name` | `keyword` | The host name of the source host |
|`vectra.timestamp` | `long` | Timestamp in seconds since epoch |
|`vectra.triaged` | `boolean` | Whether the detection has been triaged yet or not |
|`vectra.user.agent` | `keyword` | User agent |
|`vectra.user.privilege` | `long` | The observed privilege level of the host. |
|`vectra.user.role` | `keyword` | Role of the user who caused the log (e.g., admin, super admin, etc.) |

