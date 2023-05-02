Current supported interaction with Application via CLI are listed below:


## **Create an application**

```
# onqlave application add your_app_name -d your_preferred_description -t application_technology -o application_owner_id 
```

Then the returned output should include your created application ID
```
🎉 Done! Application created successfully.
Application ID: you-app-id-here
For more information, read our documentation at https://www.onqlave.com/docs
```

## **Archive an application**

```
# onqlave application archive your_app_id
```
## **Describe an application**

```
# onqlave application describe your_app_id
```

The output is formatted as a table or JSON depends on your choice of appending **--json** flag
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

```

## **Disable an application**

```
# onqlave application disable your_app_id
```

## **Enable an application**

```
# onqlave application enable your_app_id
```

## **List all applications**

```
# onqlave application list
```

## **Update an application**

Currently, Onqlave platform supports update an application via it's ID

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

## **Explore availabe commands**

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
