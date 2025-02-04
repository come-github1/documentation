
## Event Categories


The following table lists the data source offered by this integration.

| Data Source | Description                          |
| ----------- | ------------------------------------ |
| `Application logs` | Netskope logs activities on the admin console |
| `Authentication logs` | Netskope logs authentication to the admin console |
| `Third-party application logs` | Netskope monitors activites on Cloud Applications |
| `Office 365 account logs` | Netskope monitors activities on Office 365 |
| `Web proxy` | Netskope monitors HTTP traffic |





In details, the following table denotes the type of events produced by this integration.

| Name | Values |
| ---- | ------ |
| Kind | `alert` |
| Category | `authentication`, `configuration`, `file`, `iam`, `intrusion_detection`, `malware`, `network` |
| Type | `change`, `info` |




## Event Samples

Find below few samples of events and how they are normalized by SEKOIA.IO.


=== "test_audit_log_deleted_inline_policy.json"

    ```json
	
    {
        "message": "{\n  \"timestamp\": 1651451341,\n  \"type\": \"admin_audit_logs\",\n  \"user\": \"john.doe@example.org\",\n  \"severity_level\": 2,\n  \"audit_log_event\": \"Deleted inline policy\",\n  \"supporting_data\": {\n    \"data_type\": \"policy\",\n    \"data_values\": [\n      false\n    ]\n  },\n  \"organization_unit\": \"\",\n  \"ur_normalized\": \"john.doe@example.org\",\n  \"ccl\": \"unknown\",\n  \"count\": 1,\n  \"_id\": \"acfa7348-64c5-40de-b28d-202c8362d0f7\",\n  \"userPrincipalName\": \"\",\n  \"sAMAccountName\": \"\"\n}\n",
        "event": {
            "dataset": "admin_audit_logs",
            "reason": "Deleted inline policy",
            "kind": "event",
            "category": [
                "configuration"
            ],
            "type": [
                "change"
            ]
        },
        "@timestamp": "2022-05-02T00:29:01.000000Z",
        "observer": {
            "vendor": "Netskope"
        },
        "user": {
            "email": "john.doe@example.org",
            "name": "john.doe",
            "domain": "example.org"
        },
        "netskope": {
            "events": {
                "action": {
                    "type": "policy",
                    "values": [
                        false
                    ]
                },
                "ccl": "unknown",
                "severity": {
                    "level": 2
                }
            }
        },
        "related": {
            "user": [
                "john.doe"
            ]
        }
    }
    	
	```


=== "test_audit_log_edit_admin_record.json"

    ```json
	
    {
        "message": "{\n  \"timestamp\": 1651489787,\n  \"type\": \"admin_audit_logs\",\n  \"user\": \"john.doe@example.org\",\n  \"severity_level\": 1,\n  \"audit_log_event\": \"Edit admin record\",\n  \"supporting_data\": {\n    \"data_type\": \"admin\",\n    \"data_values\": [\n      \"admin@example.org\"\n    ]\n  },\n  \"organization_unit\": \"\",\n  \"ur_normalized\": \"john.doe@example.org\",\n  \"ccl\": \"unknown\",\n  \"count\": 1,\n  \"_id\": \"275a263c8f8d4b7d9e12bf65b9094116\",\n  \"userPrincipalName\": \"\",\n  \"sAMAccountName\": \"\"\n}\n",
        "event": {
            "dataset": "admin_audit_logs",
            "reason": "Edit admin record",
            "kind": "event",
            "category": [
                "configuration"
            ],
            "type": [
                "change"
            ]
        },
        "@timestamp": "2022-05-02T11:09:47.000000Z",
        "observer": {
            "vendor": "Netskope"
        },
        "user": {
            "email": "john.doe@example.org",
            "name": "john.doe",
            "domain": "example.org"
        },
        "netskope": {
            "events": {
                "action": {
                    "type": "admin",
                    "values": [
                        "admin@example.org"
                    ]
                },
                "ccl": "unknown",
                "severity": {
                    "level": 1
                }
            }
        },
        "related": {
            "user": [
                "john.doe"
            ]
        }
    }
    	
	```


=== "test_audit_log_login_failed.json"

    ```json
	
    {
        "message": "{\n  \"timestamp\": 1651494031,\n  \"type\": \"admin_audit_logs\",\n  \"user\": \"student13\",\n  \"severity_level\": 1,\n  \"audit_log_event\": \"Login Failed\",\n  \"supporting_data\": {\n    \"data_type\": \"user\",\n    \"data_values\": [\n      \"4.5.6.7\",\n      \"student13\"\n    ]\n  },\n  \"organization_unit\": \"\",\n  \"ur_normalized\": \"student13\",\n  \"ccl\": \"unknown\",\n  \"count\": 1,\n  \"_id\": \"60d81a80b26149b8a910dfffc48cbf41\",\n  \"userPrincipalName\": \"\",\n  \"sAMAccountName\": \"\"\n}\n",
        "event": {
            "dataset": "admin_audit_logs",
            "reason": "Login Failed",
            "kind": "event",
            "category": [
                "authentication"
            ],
            "type": [
                "info"
            ]
        },
        "@timestamp": "2022-05-02T12:20:31.000000Z",
        "observer": {
            "vendor": "Netskope"
        },
        "user": {
            "email": "student13",
            "name": "student13"
        },
        "netskope": {
            "events": {
                "action": {
                    "type": "user",
                    "values": [
                        "4.5.6.7",
                        "student13"
                    ]
                },
                "ccl": "unknown",
                "severity": {
                    "level": 1
                }
            }
        },
        "related": {
            "user": [
                "student13"
            ]
        }
    }
    	
	```


=== "test_audit_log_login_successful.json"

    ```json
	
    {
        "message": "{\n  \"timestamp\": 1671727087,\n  \"type\": \"admin_audit_logs\",\n  \"user\": \"john.doe@example.org\",\n  \"severity_level\": 2,\n  \"audit_log_event\": \"Login Successful\",\n  \"supporting_data\": {\n    \"data_type\": \"user\",\n    \"data_values\": [\n      \"1.2.3.4\",\n      \"john.doe@example.org\"\n    ]\n  },\n  \"organization_unit\": \"\",\n  \"ur_normalized\": \"john.doe@example.org\",\n  \"ccl\": \"unknown\",\n  \"count\": 1,\n  \"_id\": \"45b78fd638944e9ca0c6d92dfe2d4815\",\n  \"userPrincipalName\": \"\",\n  \"sAMAccountName\": \"\"\n}\n",
        "event": {
            "dataset": "admin_audit_logs",
            "reason": "Login Successful",
            "kind": "event",
            "category": [
                "authentication"
            ],
            "type": [
                "start"
            ]
        },
        "@timestamp": "2022-12-22T16:38:07.000000Z",
        "observer": {
            "vendor": "Netskope"
        },
        "user": {
            "email": "john.doe@example.org",
            "name": "john.doe",
            "domain": "example.org"
        },
        "netskope": {
            "events": {
                "action": {
                    "type": "user",
                    "values": [
                        "1.2.3.4",
                        "john.doe@example.org"
                    ]
                },
                "ccl": "unknown",
                "severity": {
                    "level": 2
                }
            }
        },
        "related": {
            "user": [
                "john.doe"
            ]
        }
    }
    	
	```


=== "test_audit_log_logout_successful.json"

    ```json
	
    {
        "message": "{\n  \"timestamp\": 1670409967,\n  \"type\": \"admin_audit_logs\",\n  \"user\": \"john.doe@example.org\",\n  \"severity_level\": 2,\n  \"audit_log_event\": \"Logout Successful\",\n  \"supporting_data\": {\n    \"data_type\": \"reason\",\n    \"data_values\": [\n      \"Logged out due to inactivity\"\n    ]\n  },\n  \"organization_unit\": \"\",\n  \"ur_normalized\": \"john.doe@example.org\",\n  \"ccl\": \"unknown\",\n  \"count\": 1,\n  \"_id\": \"e0272abae25442f681d0dbbef65b67e9\",\n  \"userPrincipalName\": \"\",\n  \"sAMAccountName\": \"\"\n}\n",
        "event": {
            "dataset": "admin_audit_logs",
            "reason": "Logout Successful",
            "kind": "event",
            "category": [
                "authentication"
            ],
            "type": [
                "end"
            ]
        },
        "@timestamp": "2022-12-07T10:46:07.000000Z",
        "observer": {
            "vendor": "Netskope"
        },
        "user": {
            "email": "john.doe@example.org",
            "name": "john.doe",
            "domain": "example.org"
        },
        "netskope": {
            "events": {
                "action": {
                    "type": "reason",
                    "values": [
                        "Logged out due to inactivity"
                    ]
                },
                "ccl": "unknown",
                "severity": {
                    "level": 2
                }
            }
        },
        "related": {
            "user": [
                "john.doe"
            ]
        }
    }
    	
	```


=== "test_audit_log_password_change_successful.json"

    ```json
	
    {
        "message": "{\n  \"timestamp\": 1651489787,\n  \"type\": \"admin_audit_logs\",\n  \"user\": \"john.doe@example.org\",\n  \"severity_level\": 1,\n  \"audit_log_event\": \"Password Change Successful\",\n  \"supporting_data\": {\n    \"data_type\": \"user\",\n    \"data_values\": [\n      \"1.2.3.4\",\n      \"admin@example.org\"\n    ]\n  },\n  \"organization_unit\": \"\",\n  \"ur_normalized\": \"john.doe@example.org\",\n  \"ccl\": \"unknown\",\n  \"count\": 1,\n  \"_id\": \"47e7e59a6ffa4662be63836a0f898b16\",\n  \"userPrincipalName\": \"\",\n  \"sAMAccountName\": \"\"\n}\n",
        "event": {
            "dataset": "admin_audit_logs",
            "reason": "Password Change Successful",
            "kind": "event",
            "category": [
                "iam"
            ],
            "type": [
                "change"
            ]
        },
        "@timestamp": "2022-05-02T11:09:47.000000Z",
        "observer": {
            "vendor": "Netskope"
        },
        "user": {
            "email": "john.doe@example.org",
            "name": "john.doe",
            "domain": "example.org"
        },
        "netskope": {
            "events": {
                "action": {
                    "type": "user",
                    "values": [
                        "1.2.3.4",
                        "admin@example.org"
                    ]
                },
                "ccl": "unknown",
                "severity": {
                    "level": 1
                }
            }
        },
        "related": {
            "user": [
                "john.doe"
            ]
        }
    }
    	
	```


=== "test_connection_log.json"

    ```json
	
    {
        "message": "{\n  \"_id\": \"69573873d4de0a4f1d2cbac4\",\n  \"access_method\": \"Client\",\n  \"app\": \"Swile\",\n  \"appcategory\": \"HR\",\n  \"bypass_reason\": \"SSL Do Not Decrypt Bypass Policy Matched\",\n  \"bypass_traffic\": \"yes\",\n  \"category\": \"HR\",\n  \"cci\": 16,\n  \"ccl\": \"poor\",\n  \"connection_id\": 0,\n  \"count\": 1,\n  \"domain\": \"test.example.org\",\n  \"dst_country\": \"FR\",\n  \"dst_geoip_src\": 1,\n  \"dst_latitude\": 48.85836410522461,\n  \"dst_location\": \"Paris\",\n  \"dst_longitude\": 2.294532060623169,\n  \"dst_region\": \"Ile-de-France\",\n  \"dst_timezone\": \"Europe/Paris\",\n  \"dst_zipcode\": \"N/A\",\n  \"dstip\": \"5.6.7.8\",\n  \"dstport\": 443,\n  \"netskope_pop\": \"FR-PAR1\",\n  \"organization_unit\": \"\",\n  \"other_categories\": [\n    \"Finance/Accounting\",\n    \"All Categories\",\n    \"HR\"\n  ],\n  \"page\": \"test.example.org\",\n  \"policy\": \"bypass_ssl for regulation purpose\",\n  \"request_id\": 1111111111111111111,\n  \"site\": \"Swile\",\n  \"src_country\": \"FR\",\n  \"src_geoip_src\": 2,\n  \"src_latitude\": 48.11,\n  \"src_location\": \"Rennes\",\n  \"src_longitude\": -1.6744,\n  \"src_region\": \"Brittany\",\n  \"src_time\": \"Wed Dec 21 17:12:00 2022\",\n  \"src_timezone\": \"Europe/Paris\",\n  \"src_zipcode\": \"35000\",\n  \"srcip\": \"4.5.6.7\",\n  \"ssl_decrypt_policy\": \"yes\",\n  \"timestamp\": 1671639140,\n  \"traffic_type\": \"CloudApp\",\n  \"transaction_id\": 0,\n  \"type\": \"connection\",\n  \"ur_normalized\": \"john.doe@example.org\",\n  \"url\": \"test.example.org\",\n  \"user\": \"john.doe@example.org\",\n  \"user_generated\": \"yes\",\n  \"userip\": \"1.2.3.4\",\n  \"userkey\": \"john.doe@example.org\",\n  \"org\": \"\",\n  \"http_transaction_count\": 0,\n  \"network\": \"\",\n  \"useragent\": \"\",\n  \"dsthost\": \"\",\n  \"numbytes\": 0,\n  \"CononicalName\": \"\",\n  \"os_version\": \"\",\n  \"browser_session_id\": 0,\n  \"resp_cnt\": 0,\n  \"log_file_name\": \"\",\n  \"suppression_end_time\": 0,\n  \"browser_version\": \"\",\n  \"severity\": \"\",\n  \"client_bytes\": 0,\n  \"suppression_start_time\": 0,\n  \"app_session_id\": 0,\n  \"sAMAccountName\": \"\",\n  \"req_cnt\": 0,\n  \"device\": \"\",\n  \"browser\": \"\",\n  \"userPrincipalName\": \"\",\n  \"conn_endtime\": 1671639139,\n  \"conn_duration\": 3,\n  \"protocol\": \"\",\n  \"fromlogs\": \"\",\n  \"serial\": \"\",\n  \"resp_content_len\": 0,\n  \"dynamic_classification\": \"\",\n  \"hostname\": \"\",\n  \"os\": \"\",\n  \"server_bytes\": 0,\n  \"conn_starttime\": 1671639136,\n  \"sessionid\": \"\",\n  \"resp_content_type\": \"\"\n}\n",
        "event": {
            "dataset": "connection",
            "reason": "SSL Do Not Decrypt Bypass Policy Matched",
            "duration": 3,
            "kind": "event",
            "start": "2022-12-21T16:12:16.000000Z",
            "end": "2022-12-21T16:12:19.000000Z",
            "category": [
                "network"
            ],
            "type": [
                "info"
            ]
        },
        "@timestamp": "2022-12-21T16:12:20.000000Z",
        "observer": {
            "vendor": "Netskope"
        },
        "user": {
            "email": "john.doe@example.org",
            "name": "john.doe",
            "domain": "example.org"
        },
        "network": {
            "bytes": 0
        },
        "source": {
            "ip": "4.5.6.7",
            "bytes": 0,
            "geo": {
                "timezone": "Europe/Paris",
                "city_name": "Rennes",
                "region_name": "Brittany",
                "postal_code": "35000",
                "country_iso_code": "FR",
                "location": {
                    "lat": 48.11,
                    "lon": -1.6744
                }
            },
            "address": "4.5.6.7"
        },
        "destination": {
            "ip": "5.6.7.8",
            "bytes": 0,
            "geo": {
                "timezone": "Europe/Paris",
                "city_name": "Paris",
                "region_name": "Ile-de-France",
                "postal_code": "N/A",
                "country_iso_code": "FR",
                "location": {
                    "lat": 48.85836410522461,
                    "lon": 2.294532060623169
                }
            },
            "address": "5.6.7.8"
        },
        "rule": {
            "name": "bypass_ssl for regulation purpose"
        },
        "url": {
            "original": "test.example.org",
            "path": "test.example.org"
        },
        "netskope": {
            "events": {
                "application": {
                    "name": "Swile",
                    "category": "HR"
                },
                "access_method": "Client",
                "ccl": "poor"
            }
        },
        "related": {
            "ip": [
                "4.5.6.7",
                "5.6.7.8"
            ],
            "user": [
                "john.doe"
            ]
        }
    }
    	
	```


=== "test_dlp_incident.json"

    ```json
	
    {
        "message": "{\"_id\":\"11fc1dee8256ff3645f6d25f06244e0ebf0d904515849b0c49f7901e2a2ad495\",\"access_method\":\"Client\",\"acting_user\":\"john.doe@example.org\",\"activity\":\"Upload\",\"app\":\"NextCloud\",\"app_session_id\":1111111111111111111,\"assignee\":\"None\",\"connection_id\":0,\"destination_app\":\"aws\",\"destination_instance_id\":\"securityforensic\",\"dlp_incident_id\":2222222222222222222,\"dlp_match_info\":[{\"dlp_action\":\"useralert\",\"dlp_forensic_id\":2222222222222222222,\"dlp_policy\":\"[DLP] Block sensitive files on Cloud Storage\",\"dlp_profile_name\":\"DLP-PII\",\"dlp_rules\":[{\"dlp_data_identifiers\":{\"industries/healthcare/medical_conditions/eng\":5,\"persons/proper_names/us/last\":5},\"dlp_incident_rule_count\":5,\"dlp_rule_name\":\"Name-Medical Condition\",\"dlp_rule_score\":10,\"dlp_rule_severity\":\"Low\",\"is_unique_count\":false,\"weighted\":false}]}],\"dlp_parent_id\":2222222222222222222,\"dst_location\":\"Paris\",\"file_lang\":\"ENGLISH\",\"file_size\":19154,\"file_type\":\"eicar.txt\",\"from_user\":\"john.doe@example.org\",\"instance_id\":\"example.org\",\"md5\":\"68b329da9893e34099c7d8ad5cb9c940\",\"object\":\"Ruby\",\"object_type\":\"Notebook\",\"referer\":\"https://intranet.example.org/\",\"severity\":\"Low\",\"site\":\"nextcloud\",\"src_location\":\"Rennes\",\"status\":\"new\",\"timestamp\":1675152713,\"title\":\"NextCloud\",\"true_obj_category\":\"Text\",\"true_obj_type\":\"Plain Text file\",\"url\":\"storage.example.org/files/eicar.txt\",\"user\":\"john.doe@example.org\",\"user_id\":\"example-netskope-repo-secu\",\"zip_file_id\":\"inci_2222222222222222222.zip\",\"exposure\":\"\",\"owner\":\"\",\"latest_incident_id\":0,\"file_path\":\"\",\"instance\":\"\",\"inline_dlp_match_info\":[],\"original_file_snapshot_id\":\"\",\"bcc\":\"\",\"to_user\":\"\",\"dlp_file\":\"\",\"classification\":\"\",\"cc\":\"\",\"owner_pdl\":\"\",\"channel\":\"\"}\n",
        "event": {
            "action": "Upload",
            "kind": "alert",
            "category": [
                "file"
            ],
            "type": [
                "info"
            ],
            "dataset": "dlp_incident"
        },
        "@timestamp": "2023-01-31T08:11:53.000000Z",
        "observer": {
            "vendor": "Netskope"
        },
        "user": {
            "email": "john.doe@example.org",
            "name": "john.doe",
            "domain": "example.org"
        },
        "source": {
            "geo": {
                "city_name": "Rennes"
            }
        },
        "destination": {
            "geo": {
                "city_name": "Paris"
            }
        },
        "url": {
            "original": "storage.example.org/files/eicar.txt",
            "path": "storage.example.org/files/eicar.txt"
        },
        "http": {
            "request": {
                "referrer": "https://intranet.example.org/"
            }
        },
        "cloud": {
            "instance": {
                "id": "example.org"
            }
        },
        "file": {
            "hash": {
                "md5": "68b329da9893e34099c7d8ad5cb9c940"
            },
            "mime_type": "eicar.txt"
        },
        "netskope": {
            "events": {
                "application": {
                    "name": "NextCloud"
                },
                "access_method": "Client"
            },
            "dlp": {
                "incident": {
                    "id": "2222222222222222222"
                }
            }
        },
        "related": {
            "hash": [
                "68b329da9893e34099c7d8ad5cb9c940"
            ],
            "user": [
                "john.doe"
            ]
        }
    }
    	
	```


=== "test_malware_alert.json"

    ```json
	
    {
        "message": "{\n  \"_id\": \"882049056ee9e069c1c329b7\",\n  \"access_method\": \"Client\",\n  \"action\": \"Detection\",\n  \"activity\": \"Download\",\n  \"alert\": \"yes\",\n  \"alert_type\": \"Malware\",\n  \"app\": \"eicar\",\n  \"app_session_id\": 111111111111111111,\n  \"appcategory\": \"n/a\",\n  \"browser\": \"Safari\",\n  \"category\": \"n/a\",\n  \"cci\": \"\",\n  \"ccl\": \"unknown\",\n  \"connection_id\": 0,\n  \"count\": 1,\n  \"device\": \"Mac Device\",\n  \"dst_country\": \"US\",\n  \"dst_geoip_src\": 2,\n  \"dst_latitude\": 47.6711,\n  \"dst_location\": \"Redmond\",\n  \"dst_longitude\": -122.1253,\n  \"dst_region\": \"Washington\",\n  \"dst_timezone\": \"America/Los_Angeles\",\n  \"dst_zipcode\": \"98073\",\n  \"dstip\": \"5.6.7.8\",\n  \"file_path\": \"NA\",\n  \"file_size\": 308,\n  \"file_type\": \"File Type Not Detected\",\n  \"hostname\": \"MacBook Pro\",\n  \"instance\": null,\n  \"managementID\": \"99999999999999999999999999999999\",\n  \"md5\": \"68b329da9893e34099c7d8ad5cb9c940\",\n  \"mime_type\": \"\",\n  \"nsdeviceuid\": \"BC848089-186A-4F2D-A26F-E5CC94C29E56\",\n  \"object\": \"eicarcom2.zip\",\n  \"object_id\": \"68b329da9893e34099c7d8ad5cb9c940\",\n  \"object_type\": \"File\",\n  \"organization_unit\": \"\",\n  \"os\": \"Monterey\",\n  \"referer\": \"https://www.eicar.org/\",\n  \"request_id\": 2222222222222222222,\n  \"severity\": \"high\",\n  \"site\": \"eicar\",\n  \"src_country\": \"FR\",\n  \"src_geoip_src\": 2,\n  \"src_latitude\": 48.11,\n  \"src_location\": \"Rennes\",\n  \"src_longitude\": -1.6744,\n  \"src_region\": \"Brittany\",\n  \"src_timezone\": \"Europe/Paris\",\n  \"src_zipcode\": \"35000\",\n  \"srcip\": \"4.3.2.1\",\n  \"timestamp\": 1671631928,\n  \"title\": \"eicarcom2.zip\",\n  \"traffic_type\": \"CloudApp\",\n  \"transaction_id\": 3333333333333333333,\n  \"tss_mode\": \"inline\",\n  \"type\": \"nspolicy\",\n  \"ur_normalized\": \"john.doe@example.org\",\n  \"url\": \"secure.eicar.org/eicarcom2.zip\",\n  \"user\": \"john.doe@example.org\",\n  \"user_id\": \"john.doe@example.org\",\n  \"userip\": \"1.2.3.4\",\n  \"userkey\": \"john.doe@example.org\",\n  \"dlp_file\": \"\",\n  \"data_center\": \"\",\n  \"browser_version\": \"\",\n  \"owner\": \"\",\n  \"dlp_incident_id\": 0,\n  \"channel_id\": \"\",\n  \"from_user_category\": \"\",\n  \"resp_cnt\": 0,\n  \"suppression_key\": \"\",\n  \"loginurl\": \"\",\n  \"total_collaborator_count\": 0,\n  \"os_version\": \"\",\n  \"dlp_rule\": \"\",\n  \"dlp_mail_parent_id\": \"\",\n  \"instance_id\": \"\",\n  \"to_user\": \"\",\n  \"suppression_end_time\": 0,\n  \"fromlogs\": \"\",\n  \"dlp_parent_id\": 0,\n  \"dstport\": 0,\n  \"dst_timezone\": \"\",\n  \"serial\": \"\",\n  \"audit_category\": \"\",\n  \"sha256\": \"\",\n  \"from_user\": \"\",\n  \"sAMAccountName\": \"\",\n  \"app_activity\": \"\",\n  \"useragent\": \"\",\n  \"netskope_activity\": \"\",\n  \"conn_duration\": 0,\n  \"other_categories\": [],\n  \"custom_connector\": \"\",\n  \"dlp_rule_severity\": \"\",\n  \"numbytes\": 0,\n  \"telemetry_app\": \"\",\n  \"true_obj_category\": \"\",\n  \"userPrincipalName\": \"\",\n  \"logintype\": \"\",\n  \"suppression_start_time\": 0,\n  \"browser_session_id\": 0,\n  \"dlp_profile\": \"\",\n  \"src_time\": \"\",\n  \"modified\": 0,\n  \"policy\": \"\",\n  \"policy_id\": \"\",\n  \"notify_template\": \"\",\n  \"audit_type\": \"\",\n  \"orignal_file_path\": \"\",\n  \"dlp_is_unique_count\": \"\",\n  \"org\": \"\",\n  \"user_category\": \"\",\n  \"dlp_unique_count\": 0,\n  \"exposure\": \"\",\n  \"netskope_pop\": \"\",\n  \"shared_with\": \"\",\n  \"client_bytes\": 0,\n  \"sanctioned_instance\": \"\",\n  \"device_classification\": \"\",\n  \"data_type\": \"\",\n  \"scan_type\": \"\",\n  \"internal_collaborator_count\": 0,\n  \"CononicalName\": \"\",\n  \"workspace\": \"\",\n  \"log_file_name\": \"\",\n  \"parent_id\": \"\",\n  \"true_obj_type\": \"\",\n  \"dlp_rule_count\": 0,\n  \"sessionid\": \"\",\n  \"workspace_id\": \"\",\n  \"page_site\": \"\",\n  \"universal_connector\": \"\",\n  \"server_bytes\": 0,\n  \"req_cnt\": 0,\n  \"file_lang\": \"\",\n  \"protocol\": \"\",\n  \"web_universal_connector\": \"\",\n  \"dsthost\": \"\",\n  \"appsuite\": \"\",\n  \"managed_app\": \"\",\n  \"page\": \"\"\n}\n",
        "event": {
            "dataset": "nspolicy",
            "action": "Download",
            "duration": 0,
            "kind": "alert",
            "category": [
                "malware"
            ],
            "type": [
                "info"
            ]
        },
        "@timestamp": "2022-12-21T14:12:08.000000Z",
        "observer": {
            "vendor": "Netskope"
        },
        "user_agent": {
            "name": "Safari"
        },
        "user": {
            "email": "john.doe@example.org",
            "name": "john.doe",
            "domain": "example.org"
        },
        "network": {
            "bytes": 0
        },
        "host": {
            "name": "MacBook Pro",
            "os": {
                "name": "Monterey",
                "type": "macos",
                "platform": "darwin"
            }
        },
        "source": {
            "ip": "4.3.2.1",
            "bytes": 0,
            "geo": {
                "timezone": "Europe/Paris",
                "city_name": "Rennes",
                "region_name": "Brittany",
                "postal_code": "35000",
                "country_iso_code": "FR",
                "location": {
                    "lat": 48.11,
                    "lon": -1.6744
                }
            },
            "address": "4.3.2.1"
        },
        "destination": {
            "ip": "5.6.7.8",
            "bytes": 0,
            "geo": {
                "city_name": "Redmond",
                "region_name": "Washington",
                "postal_code": "98073",
                "country_iso_code": "US",
                "location": {
                    "lat": 47.6711,
                    "lon": -122.1253
                }
            },
            "address": "5.6.7.8"
        },
        "url": {
            "original": "secure.eicar.org/eicarcom2.zip",
            "path": "secure.eicar.org/eicarcom2.zip"
        },
        "http": {
            "request": {
                "referrer": "https://www.eicar.org/"
            }
        },
        "file": {
            "hash": {
                "md5": "68b329da9893e34099c7d8ad5cb9c940"
            },
            "name": "eicarcom2.zip"
        },
        "netskope": {
            "alerts": {
                "type": "Malware"
            },
            "events": {
                "application": {
                    "name": "eicar",
                    "category": "n/a"
                },
                "access_method": "Client",
                "ccl": "unknown"
            }
        },
        "related": {
            "hash": [
                "68b329da9893e34099c7d8ad5cb9c940"
            ],
            "ip": [
                "4.3.2.1",
                "5.6.7.8"
            ],
            "user": [
                "john.doe"
            ]
        }
    }
    	
	```


=== "test_nspolicy_log.json"

    ```json
	
    {
        "message": "{\n  \"_id\": \"882049056ee9e069c1c329b7\",\n  \"access_method\": \"Client\",\n  \"activity\": \"Download\",\n  \"alert\": \"no\",\n  \"app\": \"Microsoft Office 365 Sharepoint Online\",\n  \"app_session_id\": 2222222222222222222,\n  \"appcategory\": \"Collaboration\",\n  \"appsuite\": \"Office365\",\n  \"browser\": \"Firefox\",\n  \"browser_session_id\": 1111111111111111111,\n  \"browser_version\": \"108.0\",\n  \"category\": \"Collaboration\",\n  \"cci\": 91,\n  \"ccl\": \"excellent\",\n  \"connection_id\": 0,\n  \"count\": 1,\n  \"device\": \"Windows Device\",\n  \"device_classification\": \"unmanaged\",\n  \"dst_country\": \"US\",\n  \"dst_geoip_src\": 2,\n  \"dst_latitude\": 47.6711,\n  \"dst_location\": \"Redmond\",\n  \"dst_longitude\": -122.1253,\n  \"dst_region\": \"Washington\",\n  \"dst_timezone\": \"America/Los_Angeles\",\n  \"dst_zipcode\": \"98073\",\n  \"dstip\": \"5.6.7.8\",\n  \"file_size\": 204299,\n  \"file_type\": \"image/gif\",\n  \"from_user\": \"john.doe@example.org\",\n  \"hostname\": \"TEST-1111111\",\n  \"instance_id\": \"Example\",\n  \"managed_app\": \"no\",\n  \"managementID\": \"\",\n  \"md5\": \"68b329da9893e34099c7d8ad5cb9c940\",\n  \"netskope_pop\": \"FR-PAR1\",\n  \"nsdeviceuid\": \"b05badf9-60ff-4b1e-a172-61a60b2f1fc4\",\n  \"object\": \"giphy2.gif\",\n  \"object_type\": \"File\",\n  \"organization_unit\": \"\",\n  \"os\": \"Windows 11\",\n  \"os_version\": \"Windows 11\",\n  \"page\": \"web.yammer.com\",\n  \"page_site\": \"Yammer\",\n  \"policy_id\": \"FCA65744E4DA5594AC16F5AD1D05216C 2022-12-21 14:31:09.981853\",\n  \"protocol\": \"HTTPS/2\",\n  \"referer\": \"https://web.yammer.com/\",\n  \"request_id\": 2471498450631098400,\n  \"sanctioned_instance\": \"\",\n  \"severity\": \"unknown\",\n  \"site\": \"Microsoft Office 365 Sharepoint Sites\",\n  \"src_country\": \"FR\",\n  \"src_geoip_src\": 2,\n  \"src_latitude\": 48.11,\n  \"src_location\": \"Rennes\",\n  \"src_longitude\": -1.6744,\n  \"src_region\": \"Brittany\",\n  \"src_time\": \"Wed Dec 21 16:52:08 2022\",\n  \"src_timezone\": \"Europe/Paris\",\n  \"src_zipcode\": \"35000\",\n  \"srcip\": \"1.2.3.4\",\n  \"telemetry_app\": \"\",\n  \"timestamp\": 1671637920,\n  \"traffic_type\": \"CloudApp\",\n  \"transaction_id\": 3333333333333333333,\n  \"tss_mode\": \"inline\",\n  \"type\": \"nspolicy\",\n  \"ur_normalized\": \"john.doe@example.org\",\n  \"url\": \"example.sharepoint.com/sites/mysite/_layouts/0/download.aspx\",\n  \"user\": \"john.doe@example.org\",\n  \"useragent\": \"Mozilla/5.0 (Windows NT 10.0; Win64; x64; rv:108.0) Gecko/20100101 Firefox/108.0\",\n  \"userip\": \"1.2.3.4\",\n  \"userkey\": \"john.doe@example.org\",\n  \"object_id\": \"\",\n  \"channel_id\": \"\",\n  \"sAMAccountName\": \"\",\n  \"dsthost\": \"\",\n  \"app_activity\": \"\",\n  \"parent_id\": \"\",\n  \"fromlogs\": \"\",\n  \"owner\": \"\",\n  \"dlp_rule_severity\": \"\",\n  \"client_bytes\": 0,\n  \"userPrincipalName\": \"\",\n  \"dlp_rule\": \"\",\n  \"dlp_unique_count\": 0,\n  \"user_id\": \"\",\n  \"dlp_incident_id\": 0,\n  \"dlp_file\": \"\",\n  \"file_path\": \"\",\n  \"dlp_parent_id\": 0,\n  \"audit_type\": \"\",\n  \"workspace_id\": \"\",\n  \"from_user_category\": \"\",\n  \"true_obj_category\": \"\",\n  \"dlp_is_unique_count\": \"\",\n  \"shared_with\": \"\",\n  \"suppression_start_time\": 0,\n  \"title\": \"\",\n  \"web_universal_connector\": \"\",\n  \"universal_connector\": \"\",\n  \"resp_cnt\": 0,\n  \"loginurl\": \"\",\n  \"req_cnt\": 0,\n  \"conn_duration\": 0,\n  \"server_bytes\": 0,\n  \"audit_category\": \"\",\n  \"sha256\": \"\",\n  \"true_obj_type\": \"\",\n  \"suppression_end_time\": 0,\n  \"custom_connector\": \"\",\n  \"netskope_activity\": \"\",\n  \"internal_collaborator_count\": 0,\n  \"notify_template\": \"\",\n  \"total_collaborator_count\": 0,\n  \"suppression_key\": \"\",\n  \"dlp_mail_parent_id\": \"\",\n  \"scan_type\": \"\",\n  \"data_center\": \"\",\n  \"dlp_rule_count\": 0,\n  \"org\": \"\",\n  \"action\": \"\",\n  \"logintype\": \"\",\n  \"exposure\": \"\",\n  \"modified\": 0,\n  \"log_file_name\": \"\",\n  \"mime_type\": \"\",\n  \"dstport\": 0,\n  \"numbytes\": 0,\n  \"to_user\": \"\",\n  \"workspace\": \"\",\n  \"instance\": \"\",\n  \"CononicalName\": \"\",\n  \"file_lang\": \"\",\n  \"other_categories\": [],\n  \"serial\": \"\",\n  \"alert_type\": \"\",\n  \"sessionid\": \"\",\n  \"orignal_file_path\": \"\",\n  \"dlp_profile\": \"\",\n  \"user_category\": \"\",\n  \"data_type\": \"\",\n  \"policy\": \"\"\n}\n",
        "event": {
            "dataset": "nspolicy",
            "action": "Download",
            "duration": 0,
            "kind": "event",
            "category": [
                "network"
            ],
            "type": [
                "info"
            ]
        },
        "@timestamp": "2022-12-21T15:52:00.000000Z",
        "observer": {
            "vendor": "Netskope"
        },
        "user_agent": {
            "name": "Firefox",
            "version": "108.0"
        },
        "user": {
            "email": "john.doe@example.org",
            "name": "john.doe",
            "domain": "example.org"
        },
        "network": {
            "bytes": 0
        },
        "host": {
            "name": "TEST-1111111",
            "os": {
                "name": "Windows 11",
                "version": "Windows 11",
                "type": "windows",
                "platform": "windows"
            }
        },
        "source": {
            "ip": "1.2.3.4",
            "bytes": 0,
            "geo": {
                "timezone": "Europe/Paris",
                "city_name": "Rennes",
                "region_name": "Brittany",
                "postal_code": "35000",
                "country_iso_code": "FR",
                "location": {
                    "lat": 48.11,
                    "lon": -1.6744
                }
            },
            "address": "1.2.3.4"
        },
        "destination": {
            "ip": "5.6.7.8",
            "bytes": 0,
            "geo": {
                "timezone": "America/Los_Angeles",
                "city_name": "Redmond",
                "region_name": "Washington",
                "postal_code": "98073",
                "country_iso_code": "US",
                "location": {
                    "lat": 47.6711,
                    "lon": -122.1253
                }
            },
            "address": "5.6.7.8"
        },
        "rule": {
            "id": "FCA65744E4DA5594AC16F5AD1D05216C 2022-12-21 14:31:09.981853"
        },
        "url": {
            "original": "example.sharepoint.com/sites/mysite/_layouts/0/download.aspx",
            "path": "example.sharepoint.com/sites/mysite/_layouts/0/download.aspx"
        },
        "http": {
            "request": {
                "referrer": "https://web.yammer.com/"
            }
        },
        "cloud": {
            "instance": {
                "id": "Example"
            }
        },
        "file": {
            "hash": {
                "md5": "68b329da9893e34099c7d8ad5cb9c940"
            },
            "mime_type": "image/gif",
            "name": "giphy2.gif"
        },
        "netskope": {
            "events": {
                "application": {
                    "name": "Microsoft Office 365 Sharepoint Online",
                    "suite": "Office365",
                    "category": "Collaboration"
                },
                "access_method": "Client",
                "ccl": "excellent"
            }
        },
        "related": {
            "hash": [
                "68b329da9893e34099c7d8ad5cb9c940"
            ],
            "ip": [
                "1.2.3.4",
                "5.6.7.8"
            ],
            "user": [
                "john.doe"
            ]
        }
    }
    	
	```


=== "test_user_alert.json"

    ```json
	
    {
        "message": "{\n  \"_id\": \"882049056ee9e069c1c329b7\",\n  \"access_method\": \"Client\",\n  \"action\": \"useralert\",\n  \"activity\": \"Share\",\n  \"alert\": \"yes\",\n  \"app\": \"WeTransfer\",\n  \"app_session_id\": 1111111111111111111,\n  \"appcategory\": \"Cloud Storage\",\n  \"browser\": \"Edge\",\n  \"browser_session_id\": 2222222222222222222,\n  \"browser_version\": \"108.0.1462.54\",\n  \"category\": \"Cloud Storage\",\n  \"cci\": 58,\n  \"ccl\": \"low\",\n  \"connection_id\": 3333333333333333333,\n  \"count\": 1,\n  \"device\": \"Windows Device\",\n  \"device_classification\": \"unmanaged\",\n  \"dst_country\": \"IE\",\n  \"dst_geoip_src\": 2,\n  \"dst_latitude\": 53.3379,\n  \"dst_location\": \"Dublin\",\n  \"dst_longitude\": -6.2591,\n  \"dst_region\": \"Leinster\",\n  \"dst_timezone\": \"Europe/Dublin\",\n  \"dst_zipcode\": \"D02\",\n  \"dstip\": \"108.128.91.183\",\n  \"from_user\": \"jane.doe@example.org\",\n  \"hostname\": \"TEST-1234\",\n  \"managed_app\": \"no\",\n  \"managementID\": \"99999999999999999999999999999999\",\n  \"netskope_pop\": \"FR-PAR1\",\n  \"notify_template\": \"useralert_justify.html\",\n  \"nsdeviceuid\": \"BC848089-186A-4F2D-A26F-E5CC94C29E56\",\n  \"object\": \"Client.exe\",\n  \"object_type\": \"File\",\n  \"organization_unit\": \"\",\n  \"os\": \"Windows 11\",\n  \"os_version\": \"Windows 11\",\n  \"page\": \"wetransfer.com/\",\n  \"page_site\": \"Web Background\",\n  \"policy\": \"DO NOT CHANGE Educate Upload to Non-Corporate Storage\",\n  \"policy_id\": \"99999999999999999999999999999999 2022-12-21 14:31:09.981853\",\n  \"protocol\": \"HTTPS/2\",\n  \"referer\": \"https://wetransfer.com/\",\n  \"request_id\": 4444444444444444444,\n  \"severity\": \"unknown\",\n  \"site\": \"WeTransfer\",\n  \"src_country\": \"FR\",\n  \"src_geoip_src\": 2,\n  \"src_latitude\": 48.11,\n  \"src_location\": \"Rennes\",\n  \"src_longitude\": -1.6744,\n  \"src_region\": \"Brittany\",\n  \"src_time\": \"Wed Dec 21 15:52:08 2022\",\n  \"src_timezone\": \"Europe/Paris\",\n  \"src_zipcode\": \"35000\",\n  \"srcip\": \"4.3.2.1\",\n  \"telemetry_app\": \"\",\n  \"timestamp\": 1671634321,\n  \"to_user\": \"a@a.fr\",\n  \"traffic_type\": \"CloudApp\",\n  \"transaction_id\": 4444444444444444444,\n  \"type\": \"nspolicy\",\n  \"ur_normalized\": \"john.doe@example.org\",\n  \"url\": \"wetransfer.com/api/v4/transfers/email\",\n  \"user\": \"john.doe@example.org\",\n  \"useragent\": \"Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/108.0.0.0 Safari/537.36 Edg/108.0.1462.54\",\n  \"userip\": \"1.2.3.4\",\n  \"userkey\": \"john.doe@example.org\",\n  \"internal_collaborator_count\": 0,\n  \"fromlogs\": \"\",\n  \"dlp_incident_id\": 0,\n  \"owner\": \"\",\n  \"dlp_profile\": \"\",\n  \"workspace\": \"\",\n  \"user_id\": \"\",\n  \"userPrincipalName\": \"\",\n  \"true_obj_category\": \"\",\n  \"dlp_is_unique_count\": \"\",\n  \"orignal_file_path\": \"\",\n  \"other_categories\": [],\n  \"serial\": \"\",\n  \"tss_mode\": \"\",\n  \"conn_duration\": 0,\n  \"from_user_category\": \"\",\n  \"md5\": \"\",\n  \"data_type\": \"\",\n  \"title\": \"\",\n  \"log_file_name\": \"\",\n  \"dstport\": 0,\n  \"exposure\": \"\",\n  \"instance_id\": \"\",\n  \"audit_category\": \"\",\n  \"netskope_activity\": \"\",\n  \"file_type\": \"\",\n  \"total_collaborator_count\": 0,\n  \"file_path\": \"\",\n  \"modified\": 0,\n  \"dlp_rule_count\": 0,\n  \"suppression_end_time\": 0,\n  \"CononicalName\": \"\",\n  \"alert_type\": \"\",\n  \"sanctioned_instance\": \"\",\n  \"suppression_start_time\": 0,\n  \"dlp_parent_id\": 0,\n  \"true_obj_type\": \"\",\n  \"dlp_mail_parent_id\": \"\",\n  \"audit_type\": \"\",\n  \"workspace_id\": \"\",\n  \"dsthost\": \"\",\n  \"web_universal_connector\": \"\",\n  \"req_cnt\": 0,\n  \"mime_type\": \"\",\n  \"suppression_key\": \"\",\n  \"scan_type\": \"\",\n  \"shared_with\": \"\",\n  \"client_bytes\": 0,\n  \"object_id\": \"\",\n  \"user_category\": \"\",\n  \"dlp_rule\": \"\",\n  \"parent_id\": \"\",\n  \"sha256\": \"\",\n  \"dlp_rule_severity\": \"\",\n  \"logintype\": \"\",\n  \"org\": \"\",\n  \"dlp_unique_count\": 0,\n  \"file_size\": 0,\n  \"instance\": \"\",\n  \"sAMAccountName\": \"\",\n  \"resp_cnt\": 0,\n  \"universal_connector\": \"\",\n  \"numbytes\": 0,\n  \"server_bytes\": 0,\n  \"channel_id\": \"\",\n  \"file_lang\": \"\",\n  \"app_activity\": \"\",\n  \"appsuite\": \"\",\n  \"sessionid\": \"\",\n  \"loginurl\": \"\",\n  \"dlp_file\": \"\",\n  \"data_center\": \"\",\n  \"custom_connector\": \"\"\n}\n",
        "event": {
            "dataset": "nspolicy",
            "action": "Share",
            "duration": 0,
            "kind": "alert",
            "category": [
                "network"
            ],
            "type": [
                "info"
            ]
        },
        "@timestamp": "2022-12-21T14:52:01.000000Z",
        "observer": {
            "vendor": "Netskope"
        },
        "user_agent": {
            "name": "Edge",
            "version": "108.0.1462.54"
        },
        "user": {
            "email": "john.doe@example.org",
            "name": "john.doe",
            "domain": "example.org"
        },
        "network": {
            "bytes": 0
        },
        "host": {
            "name": "TEST-1234",
            "os": {
                "name": "Windows 11",
                "version": "Windows 11",
                "type": "windows",
                "platform": "windows"
            }
        },
        "source": {
            "ip": "4.3.2.1",
            "bytes": 0,
            "geo": {
                "timezone": "Europe/Paris",
                "city_name": "Rennes",
                "region_name": "Brittany",
                "postal_code": "35000",
                "country_iso_code": "FR",
                "location": {
                    "lat": 48.11,
                    "lon": -1.6744
                }
            },
            "address": "4.3.2.1"
        },
        "destination": {
            "ip": "108.128.91.183",
            "bytes": 0,
            "geo": {
                "timezone": "Europe/Dublin",
                "city_name": "Dublin",
                "region_name": "Leinster",
                "postal_code": "D02",
                "country_iso_code": "IE",
                "location": {
                    "lat": 53.3379,
                    "lon": -6.2591
                }
            },
            "address": "108.128.91.183"
        },
        "rule": {
            "id": "99999999999999999999999999999999 2022-12-21 14:31:09.981853",
            "name": "DO NOT CHANGE Educate Upload to Non-Corporate Storage"
        },
        "url": {
            "original": "wetransfer.com/api/v4/transfers/email",
            "path": "wetransfer.com/api/v4/transfers/email"
        },
        "http": {
            "request": {
                "referrer": "https://wetransfer.com/"
            }
        },
        "file": {
            "name": "Client.exe"
        },
        "netskope": {
            "events": {
                "application": {
                    "name": "WeTransfer",
                    "category": "Cloud Storage"
                },
                "access_method": "Client",
                "ccl": "low"
            }
        },
        "related": {
            "ip": [
                "108.128.91.183",
                "4.3.2.1"
            ],
            "user": [
                "john.doe"
            ]
        }
    }
    	
	```





## Extracted Fields

The following table lists the fields that are extracted, normalized under the ECS format, analyzed and indexed by the parser. It should be noted that infered fields are not listed.

| Name | Type | Description                |
| ---- | ---- | ---------------------------|
|`@timestamp` | `date` | Date/time when the event originated. |
|`cloud.instance.id` | `keyword` | Instance ID of the host machine. |
|`cloud.instance.name` | `keyword` | Instance name of the host machine. |
|`destination.bytes` | `long` | Bytes sent from the destination to the source. |
|`destination.geo.city_name` | `keyword` | City name. |
|`destination.geo.country_iso_code` | `keyword` | Country ISO code. |
|`destination.geo.postal_code` | `keyword` | Postal code. |
|`destination.geo.region_name` | `keyword` | Region name. |
|`destination.geo.timezone` | `keyword` | Time zone. |
|`destination.ip` | `ip` | IP address of the destination. |
|`event.action` | `keyword` | The action captured by the event. |
|`event.category` | `keyword` | Event category. The second categorization field in the hierarchy. |
|`event.dataset` | `keyword` | Name of the dataset. |
|`event.duration` | `long` | Duration of the event in nanoseconds. |
|`event.end` | `date` | event.end contains the date when the event ended or when the activity was last observed. |
|`event.kind` | `keyword` | The kind of the event. The highest categorization field in the hierarchy. |
|`event.reason` | `keyword` | Reason why this event happened, according to the source |
|`event.start` | `date` | event.start contains the date when the event started or when the activity was first observed. |
|`event.type` | `keyword` | Event type. The third categorization field in the hierarchy. |
|`file.hash.md5` | `keyword` | MD5 hash. |
|`file.hash.sha256` | `keyword` | SHA256 hash. |
|`file.mime_type` | `keyword` | Media type of file, document, or arrangement of bytes. |
|`file.name` | `keyword` | Name of the file including the extension, without the directory. |
|`file.path` | `keyword` | Full path to the file, including the file name. |
|`host.name` | `keyword` | Name of the host. |
|`host.os.name` | `keyword` | Operating system name, without the version. |
|`host.os.platform` | `keyword` | Operating system platform (such centos, ubuntu, windows). |
|`host.os.type` | `keyword` | Which commercial OS family (one of: linux, macos, unix or windows). |
|`host.os.version` | `keyword` | Operating system version as a raw string. |
|`http.request.referrer` | `keyword` | Referrer for this HTTP request. |
|`netskope.alerts.name` | `keyword` | The name of the alert |
|`netskope.alerts.type` | `keyword` | The type of the alert |
|`netskope.dlp.incident.id` | `keyword` | The identifier of the DLP incident |
|`netskope.dlp.incident.parent_id` | `keyword` | The identifier of the DLP incident parent |
|`netskope.events.access_method` | `keyword` | The action done on the application |
|`netskope.events.action.type` | `keyword` | The name of the action |
|`netskope.events.action.values` | `array` | The targets of the action |
|`netskope.events.application.activity` | `keyword` | The action done on the application |
|`netskope.events.application.category` | `keyword` | The category of the application |
|`netskope.events.application.name` | `keyword` | The name of the application used by the user |
|`netskope.events.application.suite` | `keyword` | If the application belongs to a suite, the name of the suite |
|`netskope.events.ccl` | `keyword` | The Cloud Confidence Level |
|`netskope.events.severity.id` | `keyword` | The identifier of the severity |
|`netskope.events.severity.level` | `integer` | The level of the severity |
|`network.bytes` | `long` | Total bytes transferred in both directions. |
|`observer.name` | `keyword` | Custom name of the observer. |
|`observer.type` | `keyword` | The type of the observer the data is coming from. |
|`observer.vendor` | `keyword` | Vendor name of the observer. |
|`organization.name` | `keyword` | Organization name. |
|`rule.id` | `keyword` | Rule ID |
|`rule.name` | `keyword` | Rule name |
|`source.bytes` | `long` | Bytes sent from the source to the destination. |
|`source.geo.city_name` | `keyword` | City name. |
|`source.geo.country_iso_code` | `keyword` | Country ISO code. |
|`source.geo.postal_code` | `keyword` | Postal code. |
|`source.geo.region_name` | `keyword` | Region name. |
|`source.geo.timezone` | `keyword` | Time zone. |
|`source.ip` | `ip` | IP address of the source. |
|`url.original` | `wildcard` | Unmodified original url as seen in the event source. |
|`user.domain` | `keyword` | Name of the directory the user is a member of. |
|`user.email` | `keyword` | User email address. |
|`user.name` | `keyword` | Short name or login of the user. |
|`user.roles` | `keyword` | Array of user roles at the time of the event. |
|`user_agent.name` | `keyword` | Name of the user agent. |
|`user_agent.original` | `keyword` | Unparsed user_agent string. |
|`user_agent.version` | `keyword` | Version of the user agent. |

