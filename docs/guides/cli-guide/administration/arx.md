Current supported interaction with Arx via CLI are listed below:


## **Before you start**

If you skipped the section about <mark>**Arx's interesting meaning**</mark>, you can [catch it up here](../../../web-app-guide/administration/arx).

## **Add an Arx**

To create an Arx, simply input the following command into the CLI. Please pay attention to the flags and their availabe assigned values.
```
# onqlave arx add my_1st_arx -d "this is my first arx" -e aes-gcm-128 -i true -o your_login_email@domain.com -p gcp -u development -r au -c monthly -t serverless  
```
```                                             
Arx creation sometime takes up to 10 minutes.
If the creation is successful, the output will look similar to:
🎉 Done!  Arx created successfully.                                     
For more information, read our documentation at https://www.onqlave.com/docs
```

## **Retry adding an Arx by ID**

```
# onqlave arx retry your_arx_id
```
```
Arx creation sometime takes up to 10 minutes.
🎉 Done!  Arx created successfully.                                 
For more information, read our documentation at https://www.onqlave.com/docs
```

## **Set a default Arx**

Input command:
```
# onqlave arx default your_arx_id
```
Excpected output:
```
Setting default arx sometime takes up to 10 minutes.
🎉 Done!  Arx set default successfully.                                         
For more information, read our documentation at https://www.onqlave.com/docs
```

## **Describe an Arx by ID**

You can retrieve all information of your Arx by this command:
```
# onqlave arx describe your_arx_id
```

```
┌─────────────────────────────────────────┐
│ Key                 Value               │
│─────────────────────────────────────────│
│ Name                arx-1               │
│ SpendLimit          0                   │
│ Description                             │
│ Purpose             development         │
│ PlanID              serverless          │
│ ProviderID          gcp                 │
│ EncryptionMethodID  aes-gcm-128         │
│ RotationCycleID     3-monthly           │
│ Owner               owner_id            │
│ IsDefault           false               │
└─────────────────────────────────────────┘

```

## **List Arx**

To see a list of your Arx from CLI, simply use this command:


```
# onqlave arx list
```
The output will be formatted in tabular format
![](https://t36712295.p.clickup-attachments.com/t36712295/e886d762-d25f-4ca6-a9a2-599d3a4168bb/image.png)


There is another JSON output if you append the flag **--json** to the end of the above comand
```
List Arx =>
{
    "clusters": [
        {
            "acl": {
                "can": {
                    "delete": true,
                    "edit": true,
                    "seal": true,
                    "set_as_default": true,
                    "unseal": false
                },
                "can_not": {
                    "unseal_reason": "You don't have access to unseal the cluster as you are not the owner | only sealed clusters can be unsealed!"
                }
            },
            "availability_message": "",
            "description": "",
            "encryption_method": "aes-gcm-128",
            "id": "cluster--id_string_here",
            "is_default": false,
            "name": "my_1st_arx",
            "owner": "your_email@here.com",
            "plan": "serverless",
            "provider": "gcp",
            "purpose": "development",
            "regions": [
                "au"
            ],
            "rotation_cycle": "monthly",
            "spend_limit": 0,
            "status": "active"
        }
    ]
}
```

## **Update arx by ID**

First, to get a help of which field can be updated in an Arx, use this command:

```
# onqlave arx update -h
```

and see the help output:

```
This command is used to update arx by ID. Arx id, arx name, arx region, arx encryption method, arx rotation cycle, arx owner, arx spend limit and arx is default are required.

Usage:
  onqlave arx update [flags]

Examples:
onqlave arx update

Flags:
  -i, --arx_is_default              Enter Arx Is Default
  -n, --arx_name string             Enter Arx Name (default "test")
  -o, --arx_owner string            Enter Arx Owner (default "Default")
  -r, --arx_region string           Enter Arx Region - (AUS-EAST, AUS-WEST)
  -c, --arx_rotation_cycle string   Enter Arx Rotation Cycle (default "Default")
  -l, --arx_spend_limit uint        Enter Arx Spend Limit
  -h, --help                        help for update

Global Flags:
      --json   Output logs as JSON.  Set to true if stdout is not a TTY
```

Second, when you finish choosing the field to be updated, use this command:

```
# onqlave arx update arx_id
Flags:
  -i, --arx_is_default              Enter Arx Is Default
  -n, --arx_name string             Enter Arx Name (default "test")
  -o, --arx_owner string            Enter Arx Owner (default "Default")
  -r, --arx_region string           Enter Arx Region - (AUS-EAST, AUS-WEST)
  -c, --arx_rotation_cycle string   Enter Arx Rotation Cycle (default "Default")
  -l, --arx_spend_limit uint        Enter Arx Spend Limit
  -h, --help                        help for update

Global Flags:
      --json   Output logs as JSON.  Set to true if stdout is not a TTY.
```

Output should look like this:
```
🎉 Done! Arx updated successfully.
Arx ID: your_arx_id
For more information, read our documentation at https://www.onqlave.com/docs
```

## **Seal an Arx by ID**

To seal an Arx, include it's ID in this command:

```
# onqlave arx seal arx_id_here
```

And see the logged result:                                
```
Arx seal sometime takes up to 10 minutes.
🎉 Done!  Arx sealed successfully.                                    
For more information, read our documentation at https://www.onqlave.com/docs                                                           

```


## **Unseal an Arx by ID**

In contrary to seal, we just need to alter the command:
```
# onqlave arx unseal cluster--xQ9TpIAzI-Mf_IKm9_nAv
```

And see the result:
```
Arx unseal sometime takes up to 10 minutes.
🎉 Done!  Arx unsealed successfully.                                      
For more information, read our documentation at https://www.onqlave.com/docs
```

## **Delete an Arx by ID**

```
# onqlave arx delete your_arx_id
```
```
🎉 Done!  Arx deleted successfully.                                     
For more information, read our documentation at https://www.onqlave.com/docs
```


## **Get base configuration information for Arx**

These information may be useful when you need to input the required flags during the creation of Arx. To get these information, use the following command:
```
# onqlave arx base
```
Result would be a JSON:

```
Arx Base Information =>
{
    "encryption_methods": [
        {
            "description": "Relatively strong \u0026 faster algorithm",
            "enable": true,
            "icon": "LockIcon",
            "id": "aes-gcm-128",
            "is_default": false,
            "name": "AES-GCM-128",
            "order": 0
        },
        {
            "description": "Strong \u0026 fast algorithm",
            "enable": true,
            "icon": "LockIcon",
            "id": "aes-gcm-256",
            "is_default": true,
            "name": "AES-GCM-256",
            "order": 1
        },
        {
            "description": "Strong \u0026 high performing algorithm",
            "enable": true,
            "icon": "LockIcon",
            "id": "cha-cha-20-poly-1305",
            "is_default": false,
            "name": "CHACHA20-POLY1305",
            "order": 2
        }
    ],
    "plans": [
        {
            "description": "Highly available clusters that scale instantly",
            "enable": true,
            "icon": "ServerIcon",
            "id": "serverless",
            "is_default": true,
            "name": "Serverless",
            "order": 0
        },
        {
            "description": "Didicated single tenant clusters. For more information, contact sales@onqlave.com",
            "enable": false,
            "icon": "BoxIcon",
            "id": "dedicated",
            "is_default": false,
            "name": "Dedicated",
            "order": 1
        }
    ],
    "providers": [
        {
            "description": "",
            "enable": true,
            "id": "gcp",
            "image": "image-gcp.svg",
            "is_default": true,
            "name": "Google Cloud",
            "order": 0,
            "regions": [
                {
                    "enable": true,
                    "icon": "icon-australia.svg",
                    "id": "au",
                    "is_default": false,
                    "name": "Australia",
                    "optimisation": {
                        "message": "Highly Available",
                        "value": 100
                    },
                    "order": 0
                },
                {
                    "enable": false,
                    "icon": "icon-singapore.svg",
                    "id": "sg",
                    "is_default": false,
                    "name": "Singapore",
                    "optimisation": {
                        "message": "Highly Available",
                        "value": 100
                    },
                    "order": 0
                },
                {
                    "enable": false,
                    "icon": "icon-gb.svg",
                    "id": "gb",
                    "is_default": false,
                    "name": "United Kingdom",
                    "optimisation": {
                        "message": "Highly Available",
                        "value": 100
                    },
                    "order": 0
                },
                {
                    "enable": false,
                    "icon": "icon-usa.svg",
                    "id": "us",
                    "is_default": false,
                    "name": "USA",
                    "optimisation": {
                        "message": "Highly Available",
                        "value": 100
                    },
                    "order": 0
                }
            ]
        },
        {
            "description": "",
            "enable": false,
            "id": "aws",
            "image": "image-aws.svg",
            "is_default": false,
            "name": "AWS",
            "order": 1,
            "regions": [
                {
                    "enable": true,
                    "icon": "icon-australia.svg",
                    "id": "au",
                    "is_default": false,
                    "name": "Australia",
                    "optimisation": {
                        "message": "Highly Available",
                        "value": 100
                    },
                    "order": 0
                },
                {
                    "enable": false,
                    "icon": "icon-singapore.svg",
                    "id": "sg",
                    "is_default": false,
                    "name": "Singapore",
                    "optimisation": {
                        "message": "Highly Available",
                        "value": 100
                    },
                    "order": 0
                },
                {
                    "enable": false,
                    "icon": "icon-gb.svg",
                    "id": "gb",
                    "is_default": false,
                    "name": "United Kingdom",
                    "optimisation": {
                        "message": "Highly Available",
                        "value": 100
                    },
                    "order": 0
                },
                {
                    "enable": false,
                    "icon": "icon-usa.svg",
                    "id": "us",
                    "is_default": false,
                    "name": "USA",
                    "optimisation": {
                        "message": "Highly Available",
                        "value": 100
                    },
                    "order": 0
                }
            ]
        },
        {
            "description": "",
            "enable": false,
            "id": "azure",
            "image": "image-azure.svg",
            "is_default": false,
            "name": "Azure",
            "order": 2,
            "regions": [
                {
                    "enable": true,
                    "icon": "icon-australia.svg",
                    "id": "au",
                    "is_default": false,
                    "name": "Australia",
                    "optimisation": {
                        "message": "Highly Available",
                        "value": 100
                    },
                    "order": 0
                },
                {
                    "enable": false,
                    "icon": "icon-singapore.svg",
                    "id": "sg",
                    "is_default": false,
                    "name": "Singapore",
                    "optimisation": {
                        "message": "Highly Available",
                        "value": 100
                    },
                    "order": 0
                },
                {
                    "enable": false,
                    "icon": "icon-gb.svg",
                    "id": "gb",
                    "is_default": false,
                    "name": "United Kingdom",
                    "optimisation": {
                        "message": "Highly Available",
                        "value": 100
                    },
                    "order": 0
                },
                {
                    "enable": false,
                    "icon": "icon-usa.svg",
                    "id": "us",
                    "is_default": false,
                    "name": "USA",
                    "optimisation": {
                        "message": "Highly Available",
                        "value": 100
                    },
                    "order": 0
                }
            ]
        }
    ],
    "purposes": [
        {
            "enable": true,
            "id": "development",
            "is_default": true,
            "name": "Development",
            "order": 0
        },
        {
            "enable": true,
            "id": "testing",
            "is_default": false,
            "name": "Testing",
            "order": 1
        },
        {
            "enable": true,
            "id": "production",
            "is_default": false,
            "name": "Production",
            "order": 2
        },
        {
            "enable": true,
            "id": "staging",
            "is_default": false,
            "name": "Staging",
            "order": 3
        }
    ],
    "rotation_cycles": [
        {
            "enable": true,
            "id": "monthly",
            "is_default": false,
            "name": "Monthly",
            "order": 0
        },
        {
            "enable": true,
            "id": "3-monthly",
            "is_default": true,
            "name": "3 Monthly",
            "order": 1
        },
        {
            "enable": true,
            "id": "6-monthly",
            "is_default": false,
            "name": "6 Monthly",
            "order": 2
        },
        {
            "enable": true,
            "id": "annually",
            "is_default": false,
            "name": "Annually",
            "order": 3
        }
    ]
}
```

## **Explore the supported interaction commands with Arx**

```
# onqlave arx
This command is used to manage arx resources.

Usage:
  onqlave arx [command]

Examples:
onqlave arx

Available Commands:
  add         add arx by name and attributes
  base        get base arx info
  default     set default arx by ID
  delete      delete arx by ID
  describe    describe arx by ID
  list        list arx
  retry       retry adding arx by ID and attributes
  seal        seal arx by ID
  unseal      unseal arx by ID
  update      update arx by ID and attributes

Flags:
  -h, --help   help for arx

Global Flags:
      --json   Output logs as JSON.  Set to true if stdout is not a TTY.

Use "onqlave arx [command] --help" for more information about a command.
```