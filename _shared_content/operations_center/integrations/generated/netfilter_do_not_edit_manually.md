
## Event Categories


The following table lists the data source offered by this integration.

| Data Source | Description                          |
| ----------- | ------------------------------------ |
| `Network device logs` | Traffic events flowing through are recorded by netfilter |
| `Network protocol analysis` | Netfilter does traffic analysis at physical/data/transport layers |








## Event Samples

Find below few samples of events and how they are normalized by SEKOIA.IO.


=== "accept.json"

    ```json
	
    {
        "message": "DA->FEDERATEUR ACCEPT IN=enp4s0f0.82 OUT=enp4s0f1 MAC=14:58:d0:b4:65:b8:02:01:c0:a8:e0:26:08:00 SRC=192.168.224.43 DST=192.168.100.230 LEN=52 TOS=08 PREC=0x00 TTL=126 ID=0 DF PROTO=TCP SPT=44606 DPT=80 SEQ=2504400626 ACK=0 WINDOW=64612 SYN URGP=0 MARK=0",
        "destination": {
            "mac": "14:58:d0:b4:65:b8",
            "port": 80,
            "address": "192.168.100.230",
            "ip": "192.168.100.230"
        },
        "source": {
            "mac": "02:01:c0:a8:e0:26",
            "port": 44606,
            "address": "192.168.224.43",
            "ip": "192.168.224.43",
            "bytes": 52
        },
        "network": {
            "transport": "tcp"
        },
        "action": {
            "name": "accept",
            "outcome": "success"
        },
        "related": {
            "ip": [
                "192.168.100.230",
                "192.168.224.43"
            ]
        }
    }
    	
	```


=== "action-name.json"

    ```json
	
    {
        "message": "INPUT DFLT DROP IN=enp4s0f0.82 OUT=enp4s0f1 MAC=14:58:d0:b4:65:b8:02:01:c0:a8:e0:26:08:00 SRC=192.168.224.43 DST=192.168.100.230 LEN=52 TOS=08 PREC=0x00 TTL=126 ID=0 DF PROTO=TCP SPT=44606 DPT=80 SEQ=2504400626 ACK=0 WINDOW=64612 SYN URGP=0 MARK=0",
        "destination": {
            "mac": "14:58:d0:b4:65:b8",
            "port": 80,
            "address": "192.168.100.230",
            "ip": "192.168.100.230"
        },
        "source": {
            "mac": "02:01:c0:a8:e0:26",
            "port": 44606,
            "address": "192.168.224.43",
            "ip": "192.168.224.43",
            "bytes": 52
        },
        "network": {
            "transport": "tcp"
        },
        "action": {
            "name": "drop",
            "outcome": "success"
        },
        "related": {
            "ip": [
                "192.168.100.230",
                "192.168.224.43"
            ]
        }
    }
    	
	```


=== "action_long.json"

    ```json
	
    {
        "message": "INTERNET SPOOFING DROP  IN=enp4s0f1 OUT=enp5s0f1 MAC=14:58:d0:b4:65:bc:d8:67:d9:0f:85:41:08:00 SRC=10.16.123.245 DST=192.168.1.47 LEN=132 TOS=00 PREC=0x00 TTL=126 ID=26580 PROTO=UDP SPT=61829 DPT=65267 LEN=112 MARK=0",
        "destination": {
            "mac": "14:58:d0:b4:65:bc",
            "port": 65267,
            "address": "192.168.1.47",
            "ip": "192.168.1.47"
        },
        "source": {
            "mac": "d8:67:d9:0f:85:41",
            "port": 61829,
            "address": "10.16.123.245",
            "ip": "10.16.123.245",
            "bytes": 132
        },
        "network": {
            "transport": "udp"
        },
        "action": {
            "name": "drop",
            "outcome": "success"
        },
        "related": {
            "ip": [
                "10.16.123.245",
                "192.168.1.47"
            ]
        }
    }
    	
	```


=== "icmp.json"

    ```json
	
    {
        "message": "IPTABLES IN=net0 OUT=docker0 MAC=00:e0:4c:68:00:64:70:df:2f:d0:8c:a7:08:00 SRC=172.217.22.142 DST=172.17.0.2 LEN=84 TOS=0x00 PREC=0x00 TTL=54 ID=0 PROTO=ICMP TYPE=0 CODE=0 ID=20 SEQ=",
        "destination": {
            "mac": "00:e0:4c:68:00:64",
            "address": "172.17.0.2",
            "ip": "172.17.0.2"
        },
        "source": {
            "mac": "70:df:2f:d0:8c:a7",
            "address": "172.217.22.142",
            "ip": "172.217.22.142",
            "bytes": 84
        },
        "network": {
            "transport": "icmp"
        },
        "related": {
            "ip": [
                "172.17.0.2",
                "172.217.22.142"
            ]
        }
    }
    	
	```


=== "tcp.json"

    ```json
	
    {
        "message": "IPTABLES IN=net0 OUT=docker0 MAC=00:e0:4c:68:00:64:70:df:2f:d0:8c:a7:08:00 SRC=216.58.213.163 DST=172.17.0.2 LEN=60 TOS=0x00 PREC=0x00 TTL=120 ID=51233 PROTO=TCP SPT=80 DPT=51212 WINDOW=60192 RES=0x00 ACK SYN URGP=0",
        "destination": {
            "mac": "00:e0:4c:68:00:64",
            "port": 51212,
            "address": "172.17.0.2",
            "ip": "172.17.0.2"
        },
        "source": {
            "mac": "70:df:2f:d0:8c:a7",
            "port": 80,
            "address": "216.58.213.163",
            "ip": "216.58.213.163",
            "bytes": 60
        },
        "network": {
            "transport": "tcp"
        },
        "related": {
            "ip": [
                "172.17.0.2",
                "216.58.213.163"
            ]
        }
    }
    	
	```





## Extracted Fields

The following table lists the fields that are extracted, normalized under the ECS format, analyzed and indexed by the parser. It should be noted that infered fields are not listed.

| Name | Type | Description                |
| ---- | ---- | ---------------------------|
|`destination.address` | `keyword` | Destination network address. |
|`destination.ip` | `ip` | IP address of the destination. |
|`destination.mac` | `keyword` | MAC address of the destination. |
|`destination.port` | `long` | Port of the destination. |
|`network.transport` | `keyword` | Protocol Name corresponding to the field `iana_number`. |
|`source.address` | `keyword` | Source network address. |
|`source.bytes` | `long` | Bytes sent from the source to the destination. |
|`source.ip` | `ip` | IP address of the source. |
|`source.mac` | `keyword` | MAC address of the source. |
|`source.port` | `long` | Port of the source. |

