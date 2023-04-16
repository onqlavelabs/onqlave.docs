
## **Retrieving information**

At the moment, from the CLI, we only support retrieving information about participating users. To get all the information of your participating users, you can use this command:

```
# onqlave users list
```

The output should look like this:

```
List Users =>
{
    "users": [
        {
            "avatar": "",
            "country_code": "au",
            "createdAt": "2023-04-06T07:16:43.295363Z",
            "disable": false,
            "email_address": "your_email@host.com",
            "full_name": "John Doe",
            "id": "4iZuh5HEF7QKjfIpts7Mkey",
            "role": [
                "platform_owner"
            ],
            "status": "active",
            "tenant_id": "tenant--cr7ZHAfiY1h6keycfsPF",
            "updatedAt": "2023-04-06T07:17:55.579855Z"
        }
    ]
}                    
=====
```

To add or invite new users, you need to do it [in the GUI as explained here](../../../web-app-guide/platform/access). 