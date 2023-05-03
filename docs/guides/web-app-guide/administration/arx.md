
## **Inspiration**

The term <mark>**Arx**</mark> is actually a Latin word means [**Citadel**](https://en.wikipedia.org/wiki/Arx_(Roman)#:~:text=Arx%20is%20a%20Latin%20word%20meaning%20%22citadel%22.) that relates to a fort or a castle for the defence of a place. In the digital world, arx is associated as the castle for the defence of privacy.

![citadel-1](https://www.macmillandictionaryblog.com/wp-content/uploads/2018/11/14695-810x534.jpg)

## **Before you start**

If you are familiar with allocating cloud computing resources for your company, you will be familiar with the concept of creating and assigning clusters to support your expected workload. With Onqlave, we follow a similar approach to allow you to optimise for speed and availability.
Inside Onqlave Platform, we consider cluster as Arx.

### **Review the provided permission/role**

At our current release, there are <mark>[3 defined roles](../../platform/access.md)</mark> including Platform Owner, Platform Admin, Developer, each role has its own set of permission and <mark>[supported operations define here](../../platform/access.md)</mark>. You may need to skim through it first.

## **Create an Arx**

#### Who can perform this operation?

- [Platform Owner](../../platform/access/#1-platform-owner)

There are several configurable attributes of an Arx that are grouped into 4 sections:

- Planning
- Cloud Provider
- Region
- Encryption mechanism

We will go through all of these 4 configurable section during the creation process of an Arx.

### **1. Choose your plan**

We support you in [segregating the development, testing, staging and production](https://www.isms.online/iso-27002/control-8-31-separation-of-development-test-and-production-environments/#purpose) by providing single purposed cluster for each of your desired environment including: development, testing, staging, production.

![arx-plan](https://t36712295.p.clickup-attachments.com/t36712295/90cb27dd-6df2-427c-b33f-f5c9ca1c943a/arx-2.png){loading=lazy}

### **2. Select a provider**

The choice of cloud provider determines which service is used to store your information. This allows for you to choose a cloud provider that your organisation already uses. At present we only support Google, but more providers are coming soon.

![arx-provider](https://t36712295.p.clickup-attachments.com/t36712295/ef20bef2-a39e-44e5-a005-91b5a0899a01/arx-999.png){loading=lazy}

### **3. Select your preferred region**

The choice of region allows you to determine which geography you would like the data to reside. This may an important factor for data localisation / data residency requirements for sensitive data, whilst there can also be additional [speed and efficiency] benefits from having the data reside in the same geography as the rest of your information.

**
### **4. Select your encryption mechanism**

We only offer encryption services based on the highest performance encryption algorithms. You have the choice of AES-128, AES-256 or [CHACHA20-POLY1305](https://www.rfc-editor.org/rfc/rfc7539), with the latter offering stronger encryption but at a lower processing speed.

The key rotation frequency determines how regularly the encryption keys are changed, to ensure that your information remains safe. 

![arx-encryption](https://t36712295.p.clickup-attachments.com/t36712295/e8b7d50d-8873-40f8-b7e4-2ee8ed343834/arx-2%20(1).png){loading=lazy}

### **5. Review Ownership**

Before choose the owner, make sure that you have skimmed through the <mark>[supported access](../../platform/access)</mark> in this release.

![arx-ownership](https://t36712295.p.clickup-attachments.com/t36712295/14a22a83-1589-4b04-8b18-fb64b6adcafa/arx-2%20(2).png)

Once you have finished your selection, you can review all of them before actually create the Arx

![arx-review](https://t36712295.p.clickup-attachments.com/t36712295/1f331684-23da-419a-9cc0-b56e681de611/arx-2%20(3).png){loading=lazy}

## **View a list of Arx**

#### Who can perform this operation?

- [Platform Owner](../../platform/access/#1-platform-owner)

The overview of Arx will provide basic information about the total number of arx as well as their status.

![arx-view](https://t36712295.p.clickup-attachments.com/t36712295/dbb412a8-6071-474e-9375-380b27e0efdf/arx-2%20(4).png){loading=lazy}

## **Update an Arx**

#### Who can perform this operation?

- [Platform Owner](../../platform/access/#1-platform-owner)

There are two sections that you can make changes to your arx:

- Arx's name (in the planning section)
- The key rotation period (in the encryption section)

![arx-update](https://t36712295.p.clickup-attachments.com/t36712295/6ae882ab-752d-4f54-84cf-c0b51e770de8/arx-2%20(5).png) {loading=lazy}

## **Disable an Arx**
#### Who can perform this operation?

- [Platform Owner](../../platform/access/#1-platform-owner)

This is a feature supporting you to temporary disable an Arx and enable it in the future without having to reconfiguring everything from scratch.

![arx-seal-1](https://t36712295.p.clickup-attachments.com/t36712295/18766b61-5565-4059-983f-561dd023e84e/arx-2%20(6).png){loading=lazy,data-gallery="seal-an-arx"}

The disabling process will require the confirmation including typing exactly the name of the arx before proceeding to the next step.

![arx-seal-2](https://t36712295.p.clickup-attachments.com/t36712295/bbb55952-f71e-4cb7-95b7-e31febfbb645/arx-2%20(7).png){loading=lazy,data-gallery="seal-an-arx"}

If the disabling process is success, you can see the status of the selected arx is updated.

## **Delete an Arx**

#### Who can perform this operation?

- [Platform Owner](../../platform/access/#1-platform-owner)

To completely delete an arx, you have to go through the same process as disabling...

![arx-delete-1](https://t36712295.p.clickup-attachments.com/t36712295/9b173952-24c6-47d8-bdb4-021418567cf8/arx-2%20(9).png){loading=lazy}

... which also including typing exactly the name of the arx.

![arx-delete-2](https://t36712295.p.clickup-attachments.com/t36712295/8185d2c1-a422-4a2a-b00a-ec4b5c96c8a1/arx-2%20(10).png){loading=lazy}

Then the number of remaining arx will be updated instantly in the 

## **Not satisfied yet?**

If you have specific requirements, or would like to discuss our development plans in more details, please feel free to reach out to <product@onqlave.com>