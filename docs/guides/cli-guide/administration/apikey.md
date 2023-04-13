
## Explore availabe commands
```
# onqlave keys 

This command is used to manage api keys resources.

Usage:
  onqlave keys [command]

Examples:
onqlave keys

Available Commands:
  add         add api key by attributes
  base        get base
  delete      delete api key by ID
  describe    describe api key by ID
  list        list api keys

Flags:
  -h, --help   help for keys

Global Flags:
      --json   Output logs as JSON.  Set to true if stdout is not a TTY.

Use "onqlave keys [command] --help" for more information about a command.
```

## Retrieve necessary information
Before interacting with API keys, you may need to retrieve all the base information about arxes and aplication. The most frequently used information when interacting with API keys via CLI are IDs of arxes, application and owner

```
# onqlave keys base      
```

Output should be similar to this, including all your created arxes and applications

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

<!-- ## Create an API key
To create your api key, your have to specify your application_id, application_technology and arx_id

```
# onqlave keys add -a your_application_id -c your_arx_id -t your_application_technology
``` -->

## Desribe an API key
```
# onqlave keys describe your_app_key_id
```


## Delete an API key
```
# onqlave keys delete your_app_key_id
```


## List all API keys
```
# onqlave keys list
``` 
