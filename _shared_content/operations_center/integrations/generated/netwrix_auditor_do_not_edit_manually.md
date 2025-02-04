
## Event Categories


The following table lists the data source offered by this integration.

| Data Source | Description                          |
| ----------- | ------------------------------------ |
| `File Monitoring` | Auditor monitors files and accesses to them |





In details, the following table denotes the type of events produced by this integration.

| Name | Values |
| ---- | ------ |
| Kind | `event` |
| Category | `` |
| Type | `` |




## Event Samples

Find below few samples of events and how they are normalized by SEKOIA.IO.


=== "test_exchange_added_mailbox.json"

    ```json
	
    {
        "message": "CEF:0|Netwrix|Exchange Online|1.0|Added|Added Mailbox|0|shost=REDACTED cat=Mailbox suser=user@acme.wtf filePath=REDACTED start=d\u00e9c. 01 2022 13:40:34 GMT msg=Name: \"REDACTED\", Alias: \"REDACTED_ALIAS\", Email Address: \"redacted@acme.onmicrosoft.com\", Display Name: \"REDACTED\", Equipment: \"True\", Windows Live ID: \"redacted@acme.onmicrosoft.com\"",
        "event": {
            "kind": "event",
            "code": "added",
            "severity": 0,
            "start": "2022-12-01T13:40:34.000000Z",
            "reason": "Name: \"REDACTED\", Alias: \"REDACTED_ALIAS\", Email Address: \"redacted@acme.onmicrosoft.com\", Display Name: \"REDACTED\", Equipment: \"True\", Windows Live ID: \"redacted@acme.onmicrosoft.com\""
        },
        "observer": {
            "vendor": "Netwrix",
            "product": "Exchange Online",
            "version": "1.0"
        },
        "user": {
            "email": "user@acme.wtf"
        }
    }
    	
	```


=== "test_exchange_modified_calendar.json"

    ```json
	
    {
        "message": "CEF:0|Netwrix|Exchange Online|1.0|Modified|Modified Calendar Processing|0|shost=PAWPR07MB9321 cat=Calendar Processing suser=user@acme.tld filePath= start=d\u00e9c. 01 2022 13:41:23 GMT msg=Resource Delegates changed, All Book In Policy changed to \"False\", All Request In Policy changed to \"True\", Allow Recurring Meetings changed to \"False\", Booking Window In Days changed to \"0\", Maximum Duration In Minutes changed to \"0\"",
        "event": {
            "kind": "event",
            "code": "modified",
            "severity": 0,
            "start": "2022-12-01T13:41:23.000000Z",
            "reason": "Resource Delegates changed, All Book In Policy changed to \"False\", All Request In Policy changed to \"True\", Allow Recurring Meetings changed to \"False\", Booking Window In Days changed to \"0\", Maximum Duration In Minutes changed to \"0\""
        },
        "observer": {
            "vendor": "Netwrix",
            "product": "Exchange Online",
            "version": "1.0"
        },
        "user": {
            "email": "user@acme.tld"
        }
    }
    	
	```


=== "test_exchange_modified_conditional_access_policy.json"

    ```json
	
    {
        "message": "CEF:0|Netwrix|Exchange Online|1.0|Modified|Modified Conditional Access Policy|0|shost=redatec cat=Conditional Access Policy suser=ACME\\Administrator (Microsoft.Office.Datacenter.Torus.PowerShellWorker) filePath=some-uuid start=d\u00e9c. 01 2022 12:19:45 GMT msg=Policy Details changed to \"{\"DummyKnownNetworkPolicy\":\"\"}\", Policy Last Updated Time changed to \"12/1/2022 12:19:45 PM\", Tenant Default Policy changed to \"6\", Display Name changed to \"Policy Display Name\", Policy Identifier String changed to \"10/5/2022 7:27:35 AM\"",
        "event": {
            "kind": "event",
            "code": "modified",
            "severity": 0,
            "start": "2022-12-01T12:19:45.000000Z",
            "reason": "Policy Details changed to \"{\"DummyKnownNetworkPolicy\":\"\"}\", Policy Last Updated Time changed to \"12/1/2022 12:19:45 PM\", Tenant Default Policy changed to \"6\", Display Name changed to \"Policy Display Name\", Policy Identifier String changed to \"10/5/2022 7:27:35 AM\""
        },
        "observer": {
            "vendor": "Netwrix",
            "product": "Exchange Online",
            "version": "1.0"
        },
        "user": {
            "name": "Administrator (Microsoft.Office.Datacenter.Torus.PowerShellWorker)",
            "domain": "ACME"
        },
        "related": {
            "user": [
                "Administrator (Microsoft.Office.Datacenter.Torus.PowerShellWorker)"
            ]
        }
    }
    	
	```


=== "test_exchange_modified_mailbox.json"

    ```json
	
    {
        "message": "CEF:0|Netwrix|Exchange Online|1.0|Modified|Modified Mailbox|0|shost=REDACTED cat=Mailbox suser=user@acme.tld filePath=Redacted start=d\u00e9c. 01 2022 13:40:37 GMT msg=Office changed to \"SaaS\"",
        "event": {
            "kind": "event",
            "code": "modified",
            "severity": 0,
            "start": "2022-12-01T13:40:37.000000Z",
            "reason": "Office changed to \"SaaS\""
        },
        "observer": {
            "vendor": "Netwrix",
            "product": "Exchange Online",
            "version": "1.0"
        },
        "user": {
            "email": "user@acme.tld"
        }
    }
    	
	```


=== "test_logoff.json"

    ```json
	
    {
        "message": "CEF:0|Netwrix|Logon Activity|1.0|Logoff|Logoff Interactive logon|0|shost=server.acme.wtf cat=Interactive logon suser=Acme Domain\\user filePath=server.acme.wtf start=d\u00e9c. 01 2022 12:42:08 GMT msg=Session duration: 2 hours 1 minute.",
        "event": {
            "kind": "event",
            "code": "logoff",
            "severity": 0,
            "start": "2022-12-01T12:42:08.000000Z",
            "reason": "Session duration: 2 hours 1 minute."
        },
        "observer": {
            "vendor": "Netwrix",
            "product": "Logon Activity",
            "version": "1.0"
        },
        "user": {
            "name": "user",
            "domain": "Acme Domain"
        },
        "source": {
            "domain": "server.acme.wtf",
            "address": "server.acme.wtf",
            "top_level_domain": "wtf",
            "subdomain": "server",
            "registered_domain": "acme.wtf"
        },
        "related": {
            "hosts": [
                "server.acme.wtf"
            ],
            "user": [
                "user"
            ]
        }
    }
    	
	```


=== "test_logon_failed.json"

    ```json
	
    {
        "message": "CEF:0|Netwrix|Logon Activity|1.0|Failed Logon|Failed Logon Logon|0|shost=server.acme.tld cat=Logon suser=user filePath=N/A start=nov. 29 2022 14:51:57 GMT msg=Cause: User logon with misspelled or bad user account",
        "event": {
            "kind": "event",
            "code": "failed logon",
            "severity": 0,
            "start": "2022-11-29T14:51:57.000000Z",
            "reason": "Cause: User logon with misspelled or bad user account"
        },
        "observer": {
            "vendor": "Netwrix",
            "product": "Logon Activity",
            "version": "1.0"
        },
        "user": {
            "name": "user"
        },
        "source": {
            "domain": "server.acme.tld",
            "address": "server.acme.tld",
            "subdomain": "server.acme"
        },
        "related": {
            "hosts": [
                "server.acme.tld"
            ],
            "user": [
                "user"
            ]
        }
    }
    	
	```


=== "test_logon_success.json"

    ```json
	
    {
        "message": "CEF:0|Netwrix|Logon Activity|1.0|Successful Logon|Successful Logon Interactive logon|0|shost=server.acme.wtf cat=Interactive logon suser=domain\\user filePath=server.acme.wtf start=d\u00e9c. 01 2022 13:35:20 GMT",
        "event": {
            "kind": "event",
            "code": "successful logon",
            "severity": 0,
            "start": "2022-12-01T13:35:20.000000Z"
        },
        "observer": {
            "vendor": "Netwrix",
            "product": "Logon Activity",
            "version": "1.0"
        },
        "user": {
            "name": "user",
            "domain": "domain"
        },
        "source": {
            "domain": "server.acme.wtf",
            "address": "server.acme.wtf",
            "top_level_domain": "wtf",
            "subdomain": "server",
            "registered_domain": "acme.wtf"
        },
        "related": {
            "hosts": [
                "server.acme.wtf"
            ],
            "user": [
                "user"
            ]
        }
    }
    	
	```


=== "test_sharepoint_document_added.json"

    ```json
	
    {
        "message": "CEF:0|Netwrix|SharePoint Online|1.0|Added|Added Document|0|shost=https://acme-my.sharepoint.com/personal/redacted cat=Document suser=user@acme.tld filePath=https://acme-my.sharepoint.com/personal/redacted/Documents/redacted document name.xlsx start=d\u00e9c. 01 2022 12:38:40 GMT msg=Application Name: Microsoft Office Excel (16.0.15726.20070)",
        "event": {
            "kind": "event",
            "code": "added",
            "severity": 0,
            "start": "2022-12-01T12:38:40.000000Z",
            "action": "added document"
        },
        "observer": {
            "vendor": "Netwrix",
            "product": "SharePoint Online",
            "version": "1.0"
        },
        "user": {
            "email": "user@acme.tld"
        },
        "file": {
            "path": "personal/redacted/Documents/redacted document name.xlsx",
            "directory": "personal/redacted/Documents",
            "name": "redacted document name.xlsx"
        }
    }
    	
	```


=== "test_sharepoint_document_modified.json"

    ```json
	
    {
        "message": "CEF:0|Netwrix|SharePoint Online|1.0|Modified|Modified Document|0|shost=https://acme-my.sharepoint.com/personal/user_acme_tld cat=Document suser=user@acme.tld filePath=https://acme-my.sharepoint.com/personal/redacted/Documents/someone somestuff/Redacted.one start=nov. 29 2022 14:49:11 GMT msg=Application Name: Microsoft Office OneNote (16.0.10392.20029)",
        "event": {
            "kind": "event",
            "code": "modified",
            "severity": 0,
            "start": "2022-11-29T14:49:11.000000Z",
            "action": "modified document"
        },
        "observer": {
            "vendor": "Netwrix",
            "product": "SharePoint Online",
            "version": "1.0"
        },
        "user": {
            "email": "user@acme.tld"
        },
        "file": {
            "path": "personal/redacted/Documents/someone somestuff/Redacted.one",
            "directory": "personal/redacted/Documents/someone somestuff",
            "name": "Redacted.one"
        }
    }
    	
	```


=== "test_sharepoint_document_renamed.json"

    ```json
	
    {
        "message": "CEF:0|Netwrix|SharePoint Online|1.0|Renamed|Renamed Document|0|shost=https://acme.sharepoint.com cat=Document suser=user@acme.tld filePath=https://acme.sharepoint.com/folder one/ACME Org/user/test.txt start=nov. 29 2022 14:31:21 GMT msg=Name changed to \"test.txt\", Application Name: Microsoft OneDrive (22.227.1030.0001)",
        "event": {
            "kind": "event",
            "code": "renamed",
            "severity": 0,
            "start": "2022-11-29T14:31:21.000000Z",
            "action": "renamed document"
        },
        "observer": {
            "vendor": "Netwrix",
            "product": "SharePoint Online",
            "version": "1.0"
        },
        "user": {
            "email": "user@acme.tld"
        },
        "file": {
            "path": "folder one/ACME Org/user/test.txt",
            "directory": "folder one/ACME Org/user",
            "name": "test.txt"
        }
    }
    	
	```





## Extracted Fields

The following table lists the fields that are extracted, normalized under the ECS format, analyzed and indexed by the parser. It should be noted that infered fields are not listed.

| Name | Type | Description                |
| ---- | ---- | ---------------------------|
|`event.action` | `keyword` | The action captured by the event. |
|`event.code` | `keyword` | Identification code for this event. |
|`event.kind` | `keyword` | The kind of the event. The highest categorization field in the hierarchy. |
|`event.reason` | `keyword` | Reason why this event happened, according to the source |
|`event.severity` | `long` | Numeric severity of the event. |
|`event.start` | `date` | event.start contains the date when the event started or when the activity was first observed. |
|`file.directory` | `keyword` | Directory where the file is located. |
|`file.name` | `keyword` | Name of the file including the extension, without the directory. |
|`file.path` | `keyword` | Full path to the file, including the file name. |
|`observer.product` | `keyword` | The product name of the observer. |
|`observer.vendor` | `keyword` | Vendor name of the observer. |
|`observer.version` | `keyword` | Observer version. |
|`source.domain` | `keyword` | The domain name of the source. |
|`user.domain` | `keyword` | Name of the directory the user is a member of. |
|`user.email` | `keyword` | User email address. |
|`user.name` | `keyword` | Short name or login of the user. |

