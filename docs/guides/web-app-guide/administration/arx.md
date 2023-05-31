
## **Inspiration**

The term **Arx** is a Latin word meaning [**Citadel**](https://en.wikipedia.org/wiki/Arx_(Roman)#:~:text=Arx%20is%20a%20Latin%20word%20meaning%20%22citadel%22.) that relates to a fort or a castle providing defence for a place. In the digital world, an arx acts as a castle for the defence of privacy.

![arx-1](https://t36712295.p.clickup-attachments.com/t36712295/b5404ed7-d590-41b5-9fc7-fea9588782cb/arx-2%20(1).jpg)

## **Before you start**

If you are familiar with allocating cloud computing resources for your company, you will be familiar with the concept of creating and assigning an arx to support your expected workload. With the Onqlave platform, we follow a similar approach to allow you to optimise for speed and availability.

### **Review the provided roles and associated permissions**

Our current release includes 3 defined roles: Platform Owner, Platform Admin and Developer. Each role has its own set of permissions and supported operations. You may need to first skim through the <u>**[documentation on roles and supported operations](../../platform/access)**</u> before proceeding.

## **Create an Arx**

**Who can perform this operation?**

- **[Platform Owner](../../platform/access/#1-platform-owner)**

There are several configurable attributes of an Arx that are grouped into 4 sections:

- Planning
- Cloud Provider
- Region
- Encryption mechanism

We will go through all of these 4 configurable sections during the creation process of an Arx.

### **1. Choose your plan**

We support you in [segregating the development, testing, staging and production](https://www.isms.online/iso-27002/control-8-31-separation-of-development-test-and-production-environments/#purpose) by providing a single purpose arx for each desired environment, including: development, testing, staging, and production.

![arx-plan](https://t36712295.p.clickup-attachments.com/t36712295/1b58fbc2-634c-4436-a088-86bbe3e98c64/arx-3.png){loading=lazy}

### **2. Select a provider**

The choice of cloud provider determines which service is used to store your information. This allows for you to choose a cloud provider that your organisation already uses. At present we only support Google, but more providers are coming soon.

![arx-provider](https://t36712295.p.clickup-attachments.com/t36712295/78bc3017-eea8-4bfd-ac2b-03336f1a18cb/arx-3%20(1).png){loading=lazy}

### **3. Select your preferred region**

The choice of region allows you to determine within which geography you would like the data to reside. This may be an important factor for data localisation / data residency requirements for sensitive data, whilst there can also be additional [speed and efficiency] benefits from having the data reside in the same geography as the rest of your information.

![arx-region](https://t36712295.p.clickup-attachments.com/t36712295/3afb39a2-b82c-46d6-a247-3ba3c9954e6d/arx-3%20(2).png)

### **4. Select your encryption primitive**

We only offer encryption services based on the highest performance encryption algorithms. You have the choice of AES-GCM-128, AES-GCM-256 or XCHACHA20-POLY1305 with the latter offering stronger encryption but at a lower processing speed.

The key rotation frequency determines how regularly the encryption keys are changed. More regular rotations increase the level of security to ensure that your information remains safe.

![arx-encryption](https://t36712295.p.clickup-attachments.com/t36712295/fd851758-ce8e-4bab-bee5-65c5c65f81a5/arx-3%20(3).png){loading=lazy}

### **5. Review Ownership**

Before choosing the owner, make sure that you have skimmed through the <u>**[supported access](../../platform/access)**</u> in this release.

![arx-ownership](https://t36712295.p.clickup-attachments.com/t36712295/64b57df2-cd9b-4b0a-a4eb-7096a24f2eb5/arx-3%20(4).png)

Once you have completed all of your selections, you can review a summary of the choices before actually creating the Arx.

![arx-review](https://t36712295.p.clickup-attachments.com/t36712295/c46b8f9d-a020-4ad0-939a-715dedc4b3c4/arx-3%20(5).png){loading=lazy}

## **View a list of Arx**

**Who can perform this operation?**

- **[Platform Owner](../../platform/access/#1-platform-owner)**

The overview of Arx will provide basic information about the total number of Arx as well as their status.

![arx-view](https://t36712295.p.clickup-attachments.com/t36712295/51e8bba7-b238-4d85-be72-fdc2c02929a2/arx-3%20(6).png){loading=lazy}

## **Update an Arx**

**Who can perform this operation?**

- **[Platform Owner](../../platform/access/#1-platform-owner)**

There are two elements that you can change for any of your Arx:

- Arx's name (in the planning section)
- The key rotation period (in the encryption section)

![arx-update](https://t36712295.p.clickup-attachments.com/t36712295/3c817ede-3d64-4d45-837d-41d97762890b/arx-3%20(7).png){loading=lazy}

## **Disable an Arx**
**Who can perform this operation?**

- **[Platform Owner](../../platform/access/#1-platform-owner)**

This feature allows you to temporarily disable an Arx while maintaining the ability to enable it in the future without having to reconfigure everything from scratch.

![arx-seal-1](https://t36712295.p.clickup-attachments.com/t36712295/6bc28f17-45ac-4d5c-b09f-c2aee8d66e27/arx-3%20(8).png){loading=lazy,data-gallery="seal-an-arx"}

The disabling process will require confirmation, including typing the exact name of the Arx before proceeding to the next step.

![arx-seal-2](https://t36712295.p.clickup-attachments.com/t36712295/8a7e1193-2d33-4961-96f0-ba4fb5c95250/arx-3%20(9).png){loading=lazy,data-gallery="seal-an-arx"}

If the disabling process is successful, you can see the status of the selected Arx will have updated.

## **Delete an Arx**

**Who can perform this operation?**

- **[Platform Owner](../../platform/access/#1-platform-owner)**

To completely delete an Arx, you have to go through the same process as disabling...

![arx-delete-1](https://t36712295.p.clickup-attachments.com/t36712295/32f8757a-775f-48f3-bef5-03ab4b5f4836/arx-3%20(10).png){loading=lazy}

... which also includes typing the exact name of the Arx.

![arx-delete-2](https://t36712295.p.clickup-attachments.com/t36712295/b6d7ddb8-d8a0-449f-97e2-002c5425771c/arx-3%20(11).png){loading=lazy}

If successful, the number of remaining Arx will be updated instantly in the Arx dashboard.

## **Not satisfied yet?**

If you have specific requirements, or would like to discuss our development plans in more details, please feel free to reach out to <product@onqlave.com> or you can **directly send us a feedback via the integrated feedback button** on the lower right corner of the Arx dashboard.

![arx-feedback](https://t36712295.p.clickup-attachments.com/t36712295/0350ec17-1c27-4e03-8d79-c02433e932a2/arx-3%20(12).png)

