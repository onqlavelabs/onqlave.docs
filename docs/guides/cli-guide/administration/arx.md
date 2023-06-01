## **Inspiration**

If you skipped the section about the meaning of Arx, you can **[have a look at the previous page](../../../web-app-guide/administration/arx).**

## **Before you start**

If you are familiar with allocating cloud computing resources for your company, you will be familiar with the concept of creating and assigning Arx to support your expected workload. With Onqlave, we follow a similar approach to allow you to optimise for speed and availability.



### **Review the provided permission/role**

Our current release includes 3 defined roles: Platform Owner, Platform Admin and Developer. Each role has its own set of permissions and supported operations. You may need to first skim through the **[documentation on roles and supported operations](../../../web-app-guide/platform/access)** before proceeding.

Next, you can explore a list of **[available commands](#explore-the-supported-interaction-commands-with-arx)** or explore the **[base value of supported configuration of Arx](#get-base-configuration-information-for-arx).**

When you are ready to interact, you can go through the below list of commands to perform various operations.

## **Create an Arx**

**Who can perform this operation?**

- **[Platform Owner](../../../web-app-guide/platform/access/#1-platform-owner)**

To create an Arx, simply input the following command into the CLI. Please pay attention to the flags and their available assigned values.
There are several configurable attributes of an Arx that are grouped into 4 sections:
- **Planning**: We support you in segregating the development, testing, staging and production by providing single purposed Arx for each of your desired environments, including: development, testing, staging, and production.

- **Cloud Provider**: The choice of cloud provider determines which service is used to store your information. This allows for you to choose a cloud provider that your organisation already uses. Currently, we only support Google, but more providers are coming soon.

- **Region**: The choice of region allows you to determine within which geography you would like the data to reside. This may an important factor for data localisation / data residency requirements for sensitive data, whilst there can also be additional [speed and efficiency] benefits from having the data reside in the same geography as the rest of your information.

- **Encryption mechanism**: We only offer encryption services based on the highest performance encryption algorithms. You have the choice of AES-GCM-128, AES-GCM-256 or XCHACHA20-POLY1305, with the latter offering stronger encryption but at a lower processing speed. The key rotation frequency determines how regularly the encryption keys are changed. More regular rotations increase the level of security to ensure that your information remains safe.

You can append the *-h* or *--help* flag to the end of the add command to see the available flags:

```
# onqlave arx add -h
```
The suggested output should look like this:

```
This command is used to add arx. Valid arx name, arx provider,  arx type, arx purpose, arx region, arx description, arx encryption method, arx rotation cycle, arx owner, arx spend limit and arx is default are required.

Usage:
  onqlave arx add [flags]

Examples:
onqlave arx add

Flags:
  -d, --arx_description string         enter arx description
  -e, --arx_encryption_method string   enter arx encryption method
  -i, --arx_is_default                 enter arx is default
  -o, --arx_owner string               enter arx owner
  -p, --arx_provider string            enter arx cloud provider
  -u, --arx_purpose string             enter arx purpose
  -r, --arx_region string              enter arx region
  -c, --arx_rotation_cycle string      enter arx rotation cycle
  -l, --arx_spend_limit uint           enter arx spend limit
  -t, --arx_type string                enter arx type
  -h, --help                           help for add

Global Flags:
      --json   JSON Output. Set to true if stdout is not a TTY.
```
Next, you can explore the **[base value of supported configuration of Arx](#get-base-configuration-information-for-arx).**

After that, when you are ready, just enter the **add** command:

```
# onqlave arx add my_1st_arx -d 'this is my first arx' -e aes-gcm-128 -i true -o your_login_email@domain.com -p gcp -u development -r au -c monthly -t serverless
```

... and wait for the output logs.

```
Arx creation sometime takes up to 10 minutes.
```
If the creation is successful, the output will look similar to:
```
🎉 Done!  Arx created successfully.
Arx ID: {your-arx-id}
For more information, read our documentation at https://docs.onqlave.com/
```

## **Set a default Arx**

**Who can perform this operation?**

- **[Platform Owner](../../../web-app-guide/platform/access/#1-platform-owner)**

Input command:
```
# onqlave arx default your_arx_id
```
Expected output:
```
Setting default arx sometime takes up to 10 minutes.
🎉 Done!  Arx set default successfully.
Arx ID: {your-arx-id}
For more information, read our documentation at https://docs.onqlave.com/
```

## **Describe an Arx**

**Who can perform this operation?**

- **[Platform Owner](../../../web-app-guide/platform/access/#1-platform-owner)**

You can retrieve all information of your Arx by using this command:
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

## **View a list of Arx**

**Who can perform this operation?**

- **[Platform Owner](../../../web-app-guide/platform/access/#1-platform-owner)**

To see a list of your Arx from CLI, simply use this command:


```
# onqlave arx list
```
The output will be formatted in tabular format
![](https://t36712295.p.clickup-attachments.com/t36712295/909f1eed-e921-4371-860b-a85e0d1293b1/image.png)


<!-- There is another JSON output if you append the flag **--json** to the end of the above comand
```
List Arx =>
{
    "arx": [
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
                    "unseal_reason": "You don't have access to unseal the arx as you are not the owner | only sealed arx can be unsealed!"
                }
            },
            "availability_message": "",
            "description": "",
            "encryption_method": "aes-gcm-128",
            "id": "arx--id_string_here",
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
-->

## **Update an arx**

**Who can perform this operation?**

- **[Platform Owner](../../../web-app-guide/platform/access/#1-platform-owner)**

Firstly, to get help on which fields can be updated in an Arx, use this command:

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

Once you decide which field to update, use this command and append your list of flags and values:

```
# onqlave arx update arx_id <your_list_of_flags_and_values>
```


Output should look like this:
```
🎉 Done! Arx updated successfully.
Arx ID: your_arx_id
For more information, read our documentation at https://docs.onqlave.com
```

## **Seal an Arx**

**Who can perform this operation?**

- **[Platform Owner](../../../web-app-guide/platform/access/#1-platform-owner)**

This is a feature supporting you to temporarily disable an Arx and enable it in the future without having to reconfigure everything from scratch. To seal an Arx, include its ID in this command:

```
# onqlave arx seal arx_id_here
```

And see the logged result:
```
Arx seal sometime takes up to 10 minutes.
🎉 Done!  Arx sealed successfully.
For more information, read our documentation at https://docs.onqlave.com/

```


## **Unseal an Arx**

**Who can perform this operation?**

- **[Platform Owner](../../../web-app-guide/platform/access/#1-platform-owner)**

In contrary to seal, we just need to alter the command:
```
# onqlave arx unseal arx_id_here
```

And see the result:
```
Arx unseal sometime takes up to 10 minutes.
🎉 Done!  Arx unsealed successfully.
For more information, read our documentation at https://docs.onqlave.com/
```

## **Delete an Arx**

**Who can perform this operation?**

- **[Platform Owner](../../../web-app-guide/platform/access/#1-platform-owner)**

```
# onqlave arx delete your_arx_id
```
```
🎉 Done!  Arx deleted successfully.
For more information, read our documentation at https://docs.onqlave.com/
```


## **Get base configuration information for Arx**

This information may be useful when you need to input the required flags during the creation of an Arx. To get this information, use the following command:
```
# onqlave arx base
```
The result will be organized in a tabular format.

<!-- If you want plain JSON, just append **--json** to the end of the command. -->

![arx-base-command](https://t36712295.p.clickup-attachments.com/t36712295/70e44a5e-ae74-4820-9bf9-0ae125697a82/image.png)

<!-- JSON Output:
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
            "description": "Highly available arx that scale instantly",
            "enable": true,
            "icon": "ServerIcon",
            "id": "serverless",
            "is_default": true,
            "name": "Serverless",
            "order": 0
        },
        {
            "description": "Didicated single tenant arx. For more information, contact sales@onqlave.com",
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
-->

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
