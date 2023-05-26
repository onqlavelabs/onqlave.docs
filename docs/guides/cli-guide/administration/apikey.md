## **Before you start**

The CLI commands to manage API Keys allow you to bring your Arx and applications together. The API Keys created here will draw on all of the unique inputs you have created for the Arx and application that you chose.

When you create your key it is critical that you store it as **it will only be displayed once**. To preserve the integrity of the key, Onqlave does not keep a record of this. Do not close the final window  until you have made this record!

You may need to look at the supported [available commands for api keys](#explore-availabe-commands) and [base configuration information for API Keys](#get-base-configuration-information-for-api-keys) before working with API Keys via CLI.

## **Create an API key**

**Who can perform this operation?**

- [Platform Owner](../../platform/access/#1-platform-owner)
- [Developer](../../platform/access/#2-developer)

To create your api key, your have to specify your application_id, application_technology and arx_id

```
# onqlave key add -a your_application_id -c your_arx_id -t your_application_technology
```

The output log will include the ID of the newly created APIKey
```
🎉 Done! API Key created successfully.
API Key ID: apikey--your_api_key
For more information, read our documentation at https://docs.onqlave.com
```

## **Describe an API key**

**Who can perform this operation?**

- [Platform Owner](../../platform/access/#1-platform-owner)
- [Developer](../../platform/access/#2-developer)

```
# onqlave key describe your_app_key_id
```
Output will be formatted in tabular format

![apikey-describe](https://t36712295.p.clickup-attachments.com/t36712295/a30ee2ac-3d8f-4077-be7d-13fc95e8d209/image.png)

## **List all API keys**

**Who can perform this operation?**

- [Platform Owner](../../platform/access/#1-platform-owner)
- [Developer](../../platform/access/#2-developer)

```
# onqlave key list
```

By default, the result will be formatted in a table.
 <!-- If you want JSON format, simply appending the **--json** at the end of the above command -->

![apikey-list](https://t36712295.p.clickup-attachments.com/t36712295/7c28851f-1fa3-4f26-a8bd-910ba668916d/image.png)

## **Delete an API key**

**Who can perform this operation?**

- [Platform Owner](../../../web-app-guide/platform/access/#1-platform-owner)
- [Developer](../../../web-app-guide/platform/access/#2-developer)

```
# onqlave key delete your_app_key_id
```

## **Get base configuration information for API Keys**

Before interacting with the API key, you may need to retrieve all the base information about your Arx and application. The most frequently used information when interacting with API key via CLI are IDs of Arx, application and owner


```
# onqlave key base
```

The output should be similar to to the following:
 <!-- you can alternate the format into JSON by appending **--json** into the end of the command: -->

![api-key-base](https://t36712295.p.clickup-attachments.com/t36712295/ce103cc9-2d3a-4bce-9d30-2d6bc0795fdf/image.png)


## **Explore available commands**

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



<!-- ```
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
           "id": "app--zovKQ3NESVrtHMoPJgr5m",
           "label": "",
           "name": "Thelma Schmidt"
       }
   ],
   "arx": [
       {
           "created_by": {
               "avatar": "",
               "email_address": "your_email@gmail.com",
               "id": "Qtc2e7LVjSO7Q1tJm0PwaoeVFUS2",
               "name": "Platform"
           },
           "encryption": {
               "icon": "LockIcon",
               "id": "aes-gcm-256",
               "name": "AES-GCM-256"
           },
           "id": "arx---CSjvl4DuOygw8sYXJntm",
           "label": "",
           "name": "Marquise Douglas",
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
               "email_address": "your_email@gmail.com",
               "id": "Qtc2e7LVjSO7Q1tJm0PwaoeVFUS2",
               "name": "Platform"
           },
           "encryption": {
               "icon": "LockIcon",
               "id": "aes-gcm-256",
               "name": "AES-GCM-256"
           },
           "id": "arx--YcvryC1LtCGmTLXQUJJyP",
           "label": "",
           "name": "Horace Gibson",
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
               "email_address": "your_email@gmail.com",
               "id": "Qtc2e7LVjSO7Q1tJm0PwaoeVFUS2",
               "name": "Platform"
           },
           "encryption": {
               "icon": "LockIcon",
               "id": "aes-gcm-256",
               "name": "AES-GCM-256"
           },
           "id": "arx--v8eE3s1EnT8bYpjU2C6Wj",
           "label": "",
           "name": "Sister Jerde",
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
       }
   ]
}
```
-->
