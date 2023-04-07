Current supported interaction with Application via CLI are listed below:

# Explore availabe commands
```
# onqlave apps 
```
```
This command is used to manage applications resources.

Usage:
  onqlave apps [command]

Examples:
onqlave apps

Available Commands:
  add         add application by name and attributes
  archive     archive application by ID
  describe    describe application by ID
  disable     disable application by ID
  enable      enable application by ID
  list        list applications
  update      update application by ID and attributes

Flags:
  -h, --help   help for apps

Global Flags:
      --json   Output logs as JSON.  Set to true if stdout is not a TTY.

Use "onqlave apps [command] --help" for more information about a command.
```

# Create an application
```
# onqlave apps add your_app_name -d your_preferred_description -t application_technology -o application_owner_id 
```

# Archive an application
```
# onqlave apps archive your_app_id
```
# Describe an application
```
# onqlave apps describe your_app_id
```

# Disable an application
```
# onqlave apps disable your_app_id
```

# Enable an application
```
# onqlave apps enable your_app_id
```

# List all applications
```
# onqlave apps list
```

# Update an application
Currently, Onqlave platform supports update an application via it's ID

```
# onqlave apps update your_application_id your_list_of_flags_and_values
```

To see the available flags, you can try this command:
```
# onqlave apps update
```

And explore all the flags:

```
Usage:
  onqlave apps update [flags]

Examples:
onqlave apps update

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