
## **Retrieving information**

Currently, from the CLI, we only support retrieving information about participating users. To get all the information of your participating users, you can use this command:

```
# onqlave user list
```

The output should look like this:

![user-list](https://t36712295.p.clickup-attachments.com/t36712295/685e6c2b-83e6-4c35-8df9-ecc97b7f5417/access%2Baccount-2.png)

<!-- If you want JSON output, simply append **--json** flag to the end of the above command
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
            "id": "user_id",
            "role": [
                "platform_owner"
            ],
            "status": "active",
            "tenant_id": "your_tenant_id",
            "updatedAt": "2023-04-06T07:17:55.579855Z"
        }
    ]
}
=====
``` -->

To add or invite new users, you need to do so [in the dashboard, as explained here](../../../web-app-guide/platform/access).
