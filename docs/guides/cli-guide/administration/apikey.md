## **Before you start**

The CLI commands to manage API Keys allow you to bring your clusters and applications together. The API Keys created here will draw on all of the unique inputs you have created for the cluster and application that you choose.

When you create your key it is critical that you store it as it will only be displayed once. To preserve the integrity of the key, Onqlave does not keep a record of this. Do not close the final window  until you have made this record!

You may need to look at the supported [available commands for api keys](#explore-availabe-commands) and [base configuration information for API Keys](#get-base-configuration-information-for-api-keys) before working with API Keys via CLI.

## **Create an API key**

**Who can perform this operation?**

- [Platform Owner](../../platform/access/#1-platform-owner)
- [Developer](../../platform/access/#2-developer)

To create your api key, your have to specify your application_id, application_technology and arx_id

```
# onqlave key add -a your_application_id -c your_arx_id -t your_application_technology
```

The output log will include the ID of the newly created apikey
```
🎉 Done! API Key created successfully.
API Key ID: apikey--your_api_key
For more information, read our documentation at https://www.onqlave.com/docs
```

## **Desribe an API key**

**Who can perform this operation?**

- [Platform Owner](../../platform/access/#1-platform-owner)
- [Developer](../../platform/access/#2-developer)

```
# onqlave key describe your_app_key_id
```
Output will be formatted in tabular format

```
┌───────────────────────────────────────────────────────┐
│ Key            Value                                  │
│───────────────────────────────────────────────────────│
│ ID             apikey--43hUyLzyeVOLQE3YGj7Zw          │
│ ClusterID      cluster--IRTlZ7UswEEwUwzczWiO0         │
│ ApplicationID  app--gp-OxVE4vuxQ8jrPEh8cw        
│ CreatedAt      2023-05-02 12:27:15.147192 +0000 UTC   │
│ Status         active                                 │
│ AccessKey      Rhnlij2fJWFXvTp1DxpVdKcwpy6c2IO1       │
│ ArxUrl         https://gcp.community.serverless.au.  ────────────────────────────────────────────────────────┘
```

## **List all API key**

**Who can perform this operation?**

- [Platform Owner](../../platform/access/#1-platform-owner)
- [Developer](../../platform/access/#2-developer)

```
# onqlave key list
``` 

By default, the result will be formatted in a table. If you want JSON format, simply appending the **--json** at the end of the above command

```
┌───────────────────────────────────────────────────────┐
│ ID  AccessKey  CreatedAt   Status  ArxUrl             │
│───────────────────────────────────────────────────────│
│                                                       │
│                                                       |                │                                                       |
│                                                       |────────────────────────────────────────────────────────┘                


```

## **Delete an API key**

**Who can perform this operation?**

- [Platform Owner](../../platform/access/#1-platform-owner)
- [Developer](../../platform/access/#2-developer)

```
# onqlave key delete your_app_key_id
```

## **Explore availabe commands**

```
# onqlave key 
```

```
This command is used to manage api key resources.

Usage:
  onqlave key [command]

Examples:
onqlave key

Available Commands:
  add         add api key by attributes
  base        get base
  delete      delete api key by ID
  describe    describe api key by ID
  list        list api key

Flags:
  -h, --help   help for key

Global Flags:
      --json   Output logs as JSON.  Set to true if stdout is not a TTY.

Use "onqlave key [command] --help" for more information about a command.
```


## **Get base configuration information for API Keys**

Before interacting with API key, you may need to retrieve all the base information about arx and aplication. The most frequently used information when interacting with API key via CLI are IDs of arx, application and owner

```
# onqlave key base      
```

Output should be similar to this, including all your created arx and applications

```
API Key Base Information =>
{
    "applications": [
        {
            "application_technology": {
                "cors": false,
                "description": "",
                "enable": false,
                "icon": "ServerIcon",
                "id": "server",
                "is_default": false,
                "name": "Server",
                "order": 0
            },
            "id": "app--ID",
            "label": "",
            "name": "my_1st_app"
        }
    ],
    "clusters": [
        {
            "created_by": {
                "avatar": "",
                "email_address": "your_email@sth.com",
                "id": "owner_id",
                "name": "John Doe"
            },
            "encryption": {
                "icon": "LockIcon",
                "id": "aes-gcm-256",
                "name": "AES-GCM-256"
            },
            "id": "cluster--ID",
            "label": "",
            "name": "my_2nd_arx",
            "plan": {
                "icon": "ServerIcon",
                "name": "Serverless"
            },
            "provider": {
                "image": "image-gcp.svg",
                "name": "Google Cloud"
            },
            "purpose": {
                "name": "Development"
            },
            "regions": [
                {
                    "icon": "icon-australia.svg",
                    "name": "Australia"
                }
            ],
            "rotation_cycle": {
                "id": "3-monthly",
                "name": "3 Monthly"
            }
        },
        {
            "created_by": {
                "avatar": "",
                "email_address": "your_email@sth.com",
                "id": "owner_id",
                "name": "John Doe"
            },
            "encryption": {
                "icon": "LockIcon",
                "id": "cha-cha-20-poly-1305",
                "name": "CHACHA20-POLY1305"
            },
            "id": "cluster--ID",
            "label": "",
            "name": "my_3rd_arx",
            "plan": {
                "icon": "ServerIcon",
                "name": "Serverless"
            },
            "provider": {
                "image": "image-gcp.svg",
                "name": "Google Cloud"
            },
            "purpose": {
                "name": "Development"
            },
            "regions": [
                {
                    "icon": "icon-australia.svg",
                    "name": "Australia"
                }
            ],
            "rotation_cycle": {
                "id": "monthly",
                "name": "Monthly"
            }
        },
        {
            "created_by": {
                "avatar": "",
                "email_address": "your_email@sth.com",
                "id": "owner_id",
                "name": "John Doe"
            },
            "encryption": {
                "icon": "LockIcon",
                "id": "aes-gcm-128",
                "name": "AES-GCM-128"
            },
            "id": "cluster--ID",
            "label": "",
            "name": "my_1st_arx",
            "plan": {
                "icon": "ServerIcon",
                "name": "Serverless"
            },
            "provider": {
                "image": "image-gcp.svg",
                "name": "Google Cloud"
            },
            "purpose": {
                "name": "Development"
            },
            "regions": [
                {
                    "icon": "icon-australia.svg",
                    "name": "Australia"
                }
            ],
            "rotation_cycle": {
                "id": "3-monthly",
                "name": "3 Monthly"
            }
        }
    ]
}                    
```