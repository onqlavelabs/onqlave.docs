# **Before you start**

The related CLI commands of Application will allow you to create and allocate the unique identifiers for your front and backend applications to be used when creating API Keys. This separated Application workflow ensures you have easy access to enabling, disabling and archiving applications as needed.


When the application reference is created, an API token and encryption key is established. Note that Onqlave does not allow you to permanently delete any applications, however they can be archived, which will then disable the respective API token and encryption key.

You may need to look at the supported [available commands for application](#explore-availabe-commands)

## **Create an application**

**Who can perform this operation?**

- [Platform Owner](../../../web-app-guide/platform/access/#1-platform-owner)

```
# onqlave application add your_app_name -d your_preferred_description -t application_technology -o application_owner_id
```

Then the returned output should include your created application ID
```
🎉 Done! Application created successfully.
Application ID: you-app-id-here
For more information, read our documentation at https://docs.onqlave.com
```

## **Describe an application**

**Who can perform this operation?**

- [Platform Owner](../../../web-app-guide/platform/access/#1-platform-owner)

```
# onqlave application describe your_app_id
```

The output is formatted as a table:
 <!-- or JSON depends on your choice of appending **--json** flag -->
```
┌──────────────────────────────────────┐
│ Key          Value                   │
│──────────────────────────────────────│
│ ID           your_app_id_here        │
│ Name         app-2                   │
│ Description                          │
│ Technology   server                  │
│ Owner        owner_id                │
│ APIKeys      0                       │
│ Status       active                  │
└──────────────────────────────────────┘
```
<!-- 
```
{
   "Application": {
       "acl": {
           "can": {
               "archive": false,
               "disabled": true,
               "edit": true
           },
           "can_not": {
               "archive_reason": "Application is not disabled yet!"
           }
       },
       "api_keys": 0,
       "application_id": "your_app_id_here",
       "cors": [],
       "description": "",
       "name": "app-2",
       "owner": "owner_id",
       "status": "active",
       "technology": "server"
   }
}

``` -->

## **List all applications**

**Who can perform this operation?**

- [Platform Owner](../../../web-app-guide/platform/access/#1-platform-owner)

```
# onqlave application list
```
The output will be displayed as a table by default. 
<!-- And you can show the JSON output by appending the **--json** to the end of the above command. -->

![application-list](https://t36712295.p.clickup-attachments.com/t36712295/32dbd08e-a5ec-4758-8770-2a40c1359ab6/image.png)


## **Update an application**

**Who can perform this operation?**

- [Platform Owner](../../../web-app-guide/platform/access/#1-platform-owner)

Currently, Onqlave platform supports update an application via its ID

```
# onqlave application update your_application_id your_list_of_flags_and_values
```

To see the available flags, you can try this command:
```
# onqlave application update
```

And explore all the flags:

```
Usage:
 onqlave application update [flags]

Examples:
onqlave application update

Flags:
 -c, --application_cors string          Enter Application Cors
 -d, --application_description string   Enter Application Description
 -n, --application_name string          Enter Application Name
 -o, --application_owner string         Enter Application Owner
 -t, --application_technology string    Enter Application Technology
 -h, --help                             help for update

Global Flags:
     --json   Output logs as JSON.  Set to true if stdout is not a TTY.
```

## **Disable an application**

**Who can perform this operation?**

- [Platform Owner](../../../web-app-guide/platform/access/#1-platform-owner)

```
# onqlave application disable your_app_id
```

## **Enable an application**

**Who can perform this operation?**

- [Platform Owner](../../../web-app-guide/platform/access/#1-platform-owner)

```
# onqlave application enable your_app_id
```

## **Archive an application**

**Who can perform this operation?**

- [Platform Owner](../../../web-app-guide/platform/access/#1-platform-owner)

Since we do not support deleting applications, you can archive it. Before archiving an application, you have to disable it like the previous step.


```
# onqlave application archive your_app_id
```

## **Get base configuration information for Application**

This information may be useful when you need to input the required flags during the creation of an application. To get these information, use the following command:


```
# onqlave application base
```

Result will be organized either in tabular format by default or can be converted to JSON by appending **--json** flag at the end of the command

![application-base](https://t36712295.p.clickup-attachments.com/t36712295/6fb8663c-bccb-4362-a6a5-043668b2233b/image.png)

<!-- JSON output:
```
Application Base Information =>
{
   "technologies": [
       {
           "cors": false,
           "description": "Application which contains backend",
           "enable": false,
           "icon": "ServerIcon",
           "id": "server",
           "is_default": false,
           "name": "Server",
           "order": 0
       },
       {
           "cors": true,
           "description": "Application which contains frontend",
           "enable": false,
           "icon": "ChromeIcon",
           "id": "client",
           "is_default": false,
           "name": "Client",
           "order": 1
       }
   ]
}
``` -->

## **Explore available commands**

```
# onqlave application
```
```
This command is used to manage applications resources.

Usage:
 onqlave application [command]

Examples:
onqlave application

Available Commands:
 add         add application by name and attributes
 archive     archive application by ID
 describe    describe application by ID
 disable     disable application by ID
 enable      enable application by ID
 list        list applications
 update      update application by ID and attributes

Flags:
 -h, --help   help for application

Global Flags:
     --json   Output logs as JSON.  Set to true if stdout is not a TTY.

Use "onqlave application [command] --help" for more information about a command.
```
