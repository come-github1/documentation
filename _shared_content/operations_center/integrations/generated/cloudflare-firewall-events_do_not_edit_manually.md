
## Event Categories


The following table lists the data source offered by this integration.

| Data Source | Description                          |
| ----------- | ------------------------------------ |
| `Web application firewall logs` | Cloudflare protect web application with its web application firewall |





In details, the following table denotes the type of events produced by this integration.

| Name | Values |
| ---- | ------ |
| Kind | `event` |
| Category | `network` |
| Type | `` |




## Event Samples

Find below few samples of events and how they are normalized by SEKOIA.IO.


=== "403.json"

    ```json
	
    {
        "message": "{\"Action\":\"block\",\"ClientIP\":\"113.206.179.28\",\"ClientRequestHost\":\"foo-bar-baz.xyz\",\"ClientRequestMethod\":\"GET\",\"ClientRequestPath\":\"/static/favicon.ico\",\"ClientRequestQuery\":\"\",\"Datetime\":1657630626219000000,\"EdgeResponseStatus\":403,\"RayID\":\"7299f155dda47d6b\"}",
        "event": {
            "action": "block",
            "kind": "event",
            "category": [
                "network"
            ],
            "dataset": "firewall-events",
            "type": [
                "denied"
            ]
        },
        "@timestamp": "2022-07-12T12:57:06.219000Z",
        "source": {
            "ip": "113.206.179.28",
            "address": "113.206.179.28"
        },
        "destination": {
            "domain": "foo-bar-baz.xyz",
            "address": "foo-bar-baz.xyz",
            "top_level_domain": "xyz",
            "registered_domain": "foo-bar-baz.xyz"
        },
        "http": {
            "request": {
                "method": "GET"
            },
            "response": {
                "status_code": 403
            }
        },
        "url": {
            "domain": "foo-bar-baz.xyz",
            "path": "/static/favicon.ico",
            "top_level_domain": "xyz",
            "registered_domain": "foo-bar-baz.xyz"
        },
        "observer": {
            "vendor": "Cloudflare",
            "type": "firewall"
        },
        "cloudflare": {
            "EdgeResponseStatus": 403,
            "RayID": "7299f155dda47d6b"
        },
        "related": {
            "hosts": [
                "foo-bar-baz.xyz"
            ],
            "ip": [
                "113.206.179.28"
            ]
        }
    }
    	
	```


=== "block.json"

    ```json
	
    {
        "message": "{\"Action\":\"block\",\"ClientASN\":4562,\"ClientASNDescription\":\"PERFORMIVE\",\"ClientCountry\":\"us\",\"ClientIP\":\"10.6.12.26\",\"ClientIPClass\":\"noRecord\",\"ClientRefererHost\":\"\",\"ClientRefererPath\":\"\",\"ClientRefererQuery\":\"\",\"ClientRefererScheme\":\"\",\"ClientRequestHost\":\"foo-bar-baz.xyz\",\"ClientRequestMethod\":\"GET\",\"ClientRequestPath\":\"/.env\",\"ClientRequestProtocol\":\"HTTP/1.1\",\"ClientRequestQuery\":\"\",\"ClientRequestScheme\":\"http\",\"ClientRequestUserAgent\":\"Mozilla/5.0 (Linux; U; Android 4.4.2; en-US; HM NOTE 1W Build/KOT49H) AppleWebKit/534.30 (KHTML, like Gecko) Version/4.0 UCBrowser/11.0.5.850 U3/0.8.0 Mobile Safari/534.30\",\"Datetime\":1669858111716000000,\"EdgeColoCode\":\"EWR\",\"EdgeResponseStatus\":403,\"Kind\":\"firewall\",\"MatchIndex\":0,\"Metadata\":{\"group\":\"cloudflare_specials\",\"rule_message\":\"Version Control - Information Disclosure\"},\"OriginResponseStatus\":0,\"OriginatorRayID\":\"00\",\"RayID\":\"77280bee38a6c461\",\"RuleID\":\"100016\",\"Source\":\"waf\"}",
        "event": {
            "action": "block",
            "kind": "event",
            "category": [
                "network"
            ],
            "dataset": "firewall-events",
            "type": [
                "denied"
            ],
            "module": "cloudflare.waf"
        },
        "@timestamp": "2022-12-01T01:28:31.716000Z",
        "source": {
            "ip": "10.6.12.26",
            "geo": {
                "country_name": "us"
            },
            "address": "10.6.12.26"
        },
        "destination": {
            "domain": "foo-bar-baz.xyz",
            "address": "foo-bar-baz.xyz",
            "top_level_domain": "xyz",
            "registered_domain": "foo-bar-baz.xyz"
        },
        "http": {
            "request": {
                "method": "GET"
            },
            "version": "HTTP/1.1",
            "response": {
                "status_code": 403
            }
        },
        "url": {
            "domain": "foo-bar-baz.xyz",
            "path": "/.env",
            "scheme": "http",
            "top_level_domain": "xyz",
            "registered_domain": "foo-bar-baz.xyz"
        },
        "user_agent": {
            "original": "Mozilla/5.0 (Linux; U; Android 4.4.2; en-US; HM NOTE 1W Build/KOT49H) AppleWebKit/534.30 (KHTML, like Gecko) Version/4.0 UCBrowser/11.0.5.850 U3/0.8.0 Mobile Safari/534.30"
        },
        "network": {
            "protocol": "HTTP/1.1"
        },
        "observer": {
            "vendor": "Cloudflare",
            "type": "firewall"
        },
        "cloudflare": {
            "ClientIPClass": "noRecord",
            "ClientRefererHost": "",
            "ClientRefererPath": "",
            "ClientRefererQuery": "",
            "ClientRefererScheme": "",
            "EdgeColoCode": "EWR",
            "EdgeResponseStatus": 403,
            "Kind": "firewall",
            "OriginResponseStatus": 0,
            "OriginatorRayID": "00",
            "RayID": "77280bee38a6c461",
            "source": "waf"
        },
        "related": {
            "hosts": [
                "foo-bar-baz.xyz"
            ],
            "ip": [
                "10.6.12.26"
            ]
        }
    }
    	
	```





## Extracted Fields

The following table lists the fields that are extracted, normalized under the ECS format, analyzed and indexed by the parser. It should be noted that infered fields are not listed.

| Name | Type | Description                |
| ---- | ---- | ---------------------------|
|`@timestamp` | `date` | Date/time when the event originated. |
|`cloudflare.ClientIPClass` | `string` | The classification of the visitor’s IP address, possible values are: unknown | badHost | searchEngine | allowlist | monitoringService | noRecord | scan | tor |
|`cloudflare.ClientRefererHost` | `string` | The referer host |
|`cloudflare.ClientRefererPath` | `string` | The referer path requested by visitor |
|`cloudflare.ClientRefererQuery` | `string` | The referer query-string was requested by the visitor |
|`cloudflare.ClientRefererScheme` | `string` | The referer URL scheme requested by the visitor |
|`cloudflare.EdgeColoCode` | `string` | IATA airport code of data center that received the request |
|`cloudflare.EdgeResponseStatus` | `number` | HTTP status code returned by Cloudflare to the client |
|`cloudflare.Kind` | `string` | The dataset of the event |
|`cloudflare.OriginResponseStatus` | `number` | status returned by the origin server |
|`cloudflare.OriginatorRayID` | `string` | The RayID of the request that issued the challenge/jschallenge |
|`cloudflare.RayID` | `string` | ID of the request |
|`cloudflare.clientASNDescription` | `keyword` | The ASN of the visitor as string |
|`cloudflare.matchIndex` | `number` | Rules match index in the chain |
|`cloudflare.metadata` | `object` | Additional product-specific information. Metadata is organized in key:value pairs. Key and Value formats can vary by Cloudflare security product and can change over time |
|`cloudflare.source` | `keyword` | The Cloudflare security product triggered by this request |
|`destination.domain` | `keyword` | The domain name of the destination. |
|`event.action` | `keyword` | The action captured by the event. |
|`event.category` | `keyword` | Event category. The second categorization field in the hierarchy. |
|`event.dataset` | `keyword` | Name of the dataset. |
|`event.kind` | `keyword` | The kind of the event. The highest categorization field in the hierarchy. |
|`event.module` | `keyword` | Name of the module this data is coming from. |
|`http.request.bytes` | `long` | Total size in bytes of the request (body and headers). |
|`http.request.method` | `keyword` | HTTP request method. |
|`http.request.referrer` | `keyword` | Referrer for this HTTP request. |
|`http.response.status_code` | `long` | HTTP response status code. |
|`http.version` | `keyword` | HTTP version. |
|`network.protocol` | `keyword` | Application protocol name. |
|`observer.type` | `keyword` | The type of the observer the data is coming from. |
|`observer.vendor` | `keyword` | Vendor name of the observer. |
|`rule.id` | `keyword` | Rule ID |
|`rule.ruleset` | `keyword` | Rule ruleset |
|`source.as.number` | `long` | Unique number allocated to the autonomous system. |
|`source.geo.country_name` | `keyword` | Country name. |
|`source.ip` | `ip` | IP address of the source. |
|`source.port` | `long` | Port of the source. |
|`tls.cipher` | `keyword` | String indicating the cipher used during the current connection. |
|`tls.version_protocol` | `keyword` | Normalized lowercase protocol name parsed from original string. |
|`url.domain` | `keyword` | Domain of the url. |
|`url.path` | `wildcard` | Path of the request, such as "/search". |
|`url.query` | `keyword` | Query string of the request. |
|`url.scheme` | `keyword` | Scheme of the url. |
|`user_agent.original` | `keyword` | Unparsed user_agent string. |

