
## **Inspiration**

The term <mark>**Arx**</mark> is actually a Latin word means [**Citadel**](https://en.wikipedia.org/wiki/Arx_(Roman)#:~:text=Arx%20is%20a%20Latin%20word%20meaning%20%22citadel%22.) that relates to a fort or a castle for the defence of a place. In the digital world, arx is associated as the castle for the defence of privacy.

![citadel-1](https://www.macmillandictionaryblog.com/wp-content/uploads/2018/11/14695-810x534.jpg)

## **Before you start**

If you are familiar with allocating cloud computing resources for your company, you will be familiar with the concept of creating and assigning clusters to support your expected workload. With Onqlave, we follow a similar approach to allow you to optimise for speed and availability.
Inside Onqlave Platform, we consider cluster as Arx.

### **Review the provided permission/role**

At our current release, there are <mark>[3 defined roles](../../platform/access.md)</mark> including Platform Owner, Platform Admin, Developer, each role has its own set of permission and <mark>[supported operations define here](../../platform/access.md)</mark>. You may need to skim through it first.

## **Create an Arx**

#### Who can perform this operations?

- [Platform Owner](http://localhost:8000/guides/web-app-guide/platform/access/#1-platform-owner)

There are several configurable attributes of an Arx that are grouped into 4 sections:

- Planning
- Cloud Provider
- Region
- Encryption mechanism

We will go through all of these 4 configurable section during the creation process of an Arx.

### **1. Choose your plan**

We support you in [segregating the development, testing, staging and production](https://www.isms.online/iso-27002/control-8-31-separation-of-development-test-and-production-environments/#purpose) by providing single purposed cluster for each of your desired environment including: development, testing, staging, production.

![arx-plan](https://t36712295.p.clickup-attachments.com/t36712295/ca49093e-0fbd-43fc-a61b-82712fd4bcaf/arx.png){loading=lazy}

### **2. Select a provider**

The choice of cloud provider determines which service is used to store your information. This allows for you to choose a cloud provider that your organisation already uses. At present we only support Google, but more providers are coming soon.

![arx-provider](https://t36712295.p.clickup-attachments.com/t36712295/98028c77-f5ab-468b-b32d-ffc22c7a675c/arx%20(2).png){loading=lazy}

### **3. Select your preferred region**

The choice of region allows you to determine which geography you would like the data to reside. This may an important factor for data localisation / data residency requirements for sensitive data, whilst there can also be additional [speed and efficiency] benefits from having the data reside in the same geography as the rest of your information.

![arx-region](https://t36712295.p.clickup-attachments.com/t36712295/554c4143-f305-4e16-9b8d-43b2340dc80a/arx%20(3).png){loading=lazy}
**
### **4. Select your encryption mechanism**

We only offer encryption services based on the highest performance encryption algorithms. You have the choice of AES-128, AES-256 or [CHACHA20-POLY1305](https://www.rfc-editor.org/rfc/rfc7539), with the latter offering stronger encryption but at a lower processing speed.

The key rotation frequency determines how regularly the encryption keys are changed, to ensure that your information remains safe. 

![arx-encryption](https://t36712295.p.clickup-attachments.com/t36712295/bafe48e8-7065-4351-aa69-9773e71d88e6/arx%20(4).png){loading=lazy}

Once you have finished your selection, you can review all of them before actually create the Arx

![arx-review](https://t36712295.p.clickup-attachments.com/t36712295/9e5a3119-d5ee-486a-8aba-081a053b67e7/arx%20(6).png){loading=lazy}

## **View a list of Arx**

#### Who can perform this operations?

- [Platform Owner](http://localhost:8000/guides/web-app-guide/platform/access/#1-platform-owner)

The overview of Arx will provide basic information about the total number of arx as well as their status.

![arx-view](https://t36712295.p.clickup-attachments.com/t36712295/7a37bb03-01cf-4ffa-92a9-bdea221a5cf1/arx%20(7).png){loading=lazy}

## **Update an Arx**

#### Who can perform this operations?

- [Platform Owner](http://localhost:8000/guides/web-app-guide/platform/access/#1-platform-owner)

There are two sections that you can make changes to your arx:

- Arx's name (in the planning section)
- The key rotation period (in the encryption section)

![arx-update](https://t36712295.p.clickup-attachments.com/t36712295/39041c90-21b2-48f5-b761-b41e3b5e6bb0/arx-15.png){loading=lazy}

## **Disable an Arx**
#### Who can perform this operations?

- [Platform Owner](http://localhost:8000/guides/web-app-guide/platform/access/#1-platform-owner)

This is a feature supporting you to temporary disable an Arx and enable it in the future without having to reconfiguring everything from scratch.

![arx-seal-1](https://t36712295.p.clickup-attachments.com/t36712295/4be81950-163e-43db-acdb-4661275b48cf/arx%20(8).png){loading=lazy,data-gallery="seal-an-arx"}

The disabling process will require the confirmation including typing exactly the name of the arx before proceeding to the next step.

![arx-seal-2](https://t36712295.p.clickup-attachments.com/t36712295/e907a6f8-3c2c-4450-8434-f3782f650145/arx%20(9).png){loading=lazy,data-gallery="seal-an-arx"}

If the disabling process is success, you can see the status of the selected arx is updated.

![arx-seal-3](https://t36712295.p.clickup-attachments.com/t36712295/38d15d6d-1c44-467e-be4a-b624f6c9071e/arx%20(10).png){loading=lazy,data-gallery="seal-an-arx"}

## **Delete an Arx**

#### Who can perform this operations?

- [Platform Owner](http://localhost:8000/guides/web-app-guide/platform/access/#1-platform-owner)

To completely delete an arx, you have to go through the same process as disabling...

![arx-delete-1](https://t36712295.p.clickup-attachments.com/t36712295/3e7e01bb-5a8c-4273-8b26-5726dac7acc1/arx%20(12).png){loading=lazy}

... which also including typing exactly the name of the arx.

![arx-delete-2](https://t36712295.p.clickup-attachments.com/t36712295/9c902b9e-85cd-4135-8f49-ca99306904b7/arx%20(13).png){loading=lazy}

Then the number of remaining arx will be updated instantly in the Arx dashboard.

![arx-delete-3](https://t36712295.p.clickup-attachments.com/t36712295/2e8a6cd1-e5b1-4459-9bfd-9ccc0d2ea261/arx%20(14).png){loading=lazy}

## **Not satisfied yet?**

If you have specific requirements, or would like to discuss our development plans in more details, please feel free to reach out to <product@onqlave.com>