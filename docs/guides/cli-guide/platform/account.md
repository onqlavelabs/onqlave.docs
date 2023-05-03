
## **Before you start**

You can refer to [this section on the GUI](../../../web-app-guide/platform/account) for better understanding.

Or you can refer to [this section for getting help about available commands](../../overview-cli/#looking-for-another-way-of-interaction).

## **Retrieving tenant information**

You can use this command to retrieve the organization/tenant information:

```
# onqlave tenant describe
```

The result should look like this:

```
Tenant 'tenant--cr7ZHkeyjdWycfsPF' Information =>
{
    "data": {
        "acl": {
            "can": {
                "edit": true
            },
            "can_not": null
        },
        "created_on": "2023-04-06T07:16:44.169507Z",
        "owner_email": "your_email@host.com",
        "tenant_id": "tenant--cr7ZHkeyjdWycfsPF",
        "tenant_label": "dc",
        "tenant_name": "dc-tenant-1"
    },
    "error": {
        "code": 0,
        "correlation_id": "",
        "details": null,
        "message": "",
        "status": ""
    }
}
```

## **Updating tenant information**
There are two fields that you can update: **label** and **name**

```
# onqlave tenants update -l dcm -n dc-tenant-1-updated
```

The successful output is simply like this:

```
🎉 Done!  Tenant updated successfully
```

You can double check the updated result by using the **describe** command above:

```
┌────────────────────────────────────────────┐
│ Key          Value                         │
│────────────────────────────────────────────│
│ Id           tenant--B8dxGtiyx2CWG8mYtvpfr │
│ Name         dev-tenant-1-updated          │
│ Label        your_label                    │
│ OwnerEmail   po.onclave@gmail.com          │
└────────────────────────────────────────────┘
```

## **Explore availabe commands**

```
# onqlave tenant 
```

```
This command is used to manage tenants resource.

Usage:
  onqlave tenant [command]

Examples:
onqlave tenant

Available Commands:
  describe    describe tenant
  update      update tenant by name and label

Flags:
  -h, --help   help for tenant

Global Flags:
      --json   JSON Output. Set to true if stdout is not a TTY.

Use "onqlave tenant [command] --help" for more information about a command.
```