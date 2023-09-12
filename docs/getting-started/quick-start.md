
## **Get started building with Onqlave in minutes**

In this short guide, you'll learn key concepts and experience the Onqlave workflow. It should only take about **5 minutes** to complete and by the end you'll have an up and running Encryption infrastructure in Onqlave's free development Cloud (Onqlave Community Cloud).

To make it easy to follow along, we've laid out a trail of emojis to guide your way. Whenever you see a 🥐 it means there's something for you to do.

**Let's get started!**

## **1. Install the Onqlave CLI**

To develop with Onqlave, you need the Onqlave CLI (can be done through Dashboard as well). It provisions your test environment, and set up what you need to use Onqlave for development.

🥐 Install by running the appropriate command for your system:

### **Linux**

- Download Linux executable file `onqlave-linux` from the [release assets](https://github.com/onqlavelabs/onqlave.cli/releases/tag/v0.6.0)
- Grant executable permission to `onqlave-linux` file

```
sudo chmod +x onqlave-linux
```

- Make sure `onqlave-linux` is executable:

```
./onqlave-linux
```
### **MacOS**

- Download Linux executable file `onqlave-darwin` from the [release assets](https://github.com/onqlavelabs/onqlave.cli/releases/tag/v0.6.0)
- Grant executable permission to `onqlave-darwin` file

```
sudo chmod +x onqlave-darwin
```

- Make sure `onqlave-darwin` is executable:

```
./onqlave-darwin
```

### **Windows**

- Download Windows executable file `onqlave-windows.exe` from the [release assets](https://github.com/onqlavelabs/onqlave.cli/releases/tag/v0.6.0)
- Make sure `onqlave-windows.exe` is executable:

```
.\onqlave-windows.exe
```

### **Docker**

Use this command to get our latest docker image:

```
docker pull ghcr.io/onqlavelabs/onqlavelabs/onqlave.cli:latest
```

Listing all the existed docker images of Onqlave:

```
docker image ls | grep ghcr.io/onqlavelabs/onqlavelabs/onqlave.cli
```

From here you can observe the latest image_id and can copy it to include in the next command to run the image or you can simply run this command to start the container:

```
docker run -it ghcr.io/onqlavelabs/onqlavelabs/onqlave.cli bash
```

After entering the container via BASH shell, you can try to type this command to make sure everything works:

```
onqlave
```

### **Installation Script**

- An installation shell script is provided to download any specific Onqlave CLI version
- Download and execute the installation script:

```shell
curl -s "https://raw.githubusercontent.com/onqlavelabs/onqlave.cli/main/scripts/install.sh" | bash -s ${cli-version}
```

- For Windows users, it is recommended to have bash executable installed such as `git bash` before using the
  installation script; or you can download the CLI executable directly from the release.

## **2. Init the Onqlave CLI environment**

To be able to use Onqlave CLI, you would need to first initialise the CLI. 

🥐 Initialise by running the following command:

```
onqlave config init
```

## **3. Signup to Onqlave Platform**

Now you have your CLI configured, you will need to setup your Onqlave account.

🥐 Signup by running the following command:

```
onqlave auth signup your_email@domain.com --full_name="You Full Name" --tenant_name="Your tenant name"
```

🥐 Login by running the following command:

```
onqlave auth login your_email@domain.com --tenant_name="Your tenant name"
```

## **4. Create your first API key**

Now you have your Onqlave account, you can create your first API key which can be used to integrate your application with Onqlave Encryption Engine using our SDKs.

Note: API key should be treated a secret. So make sure you keep it secure, maybe storing it in your secret manager, or environment variable - don't hardcode it :)

🥐 Create API Key by running the following command:

```
onqlave key add -a your_application_id -c your_arx_id -t your_application_technology
```

## **5. Find Onqlave SDK for your language of choice**

Now that you have your first API Key, you can use our SDKs to integrate with your application. After that you would be able to easily encrypt/decrypt any piece of data.

🥐 Choose and download your preferred SDK:

1. [Go SDK](https://docs.onqlave.com/guides/sdks/sdk-go/)


2. [NodeJS SDK](https://docs.onqlave.com/guides/sdks/sdk-node/)


3. [Java SDK](https://docs.onqlave.com/guides/sdks/sdk-java/)


4. [Python SDK](https://docs.onqlave.com/guides/sdks/sdk-py/)




## **6. Encrypt/Decrypt your sensitive information**

You are now ready to encrypt/decrypt data in your application using Onqlave Encryption engine.

🥐 Encrypt/Decrypt with these example codes:

### Init the encryption 

**1. Go**

```go
import (
	"github.com/onqlavelabs/onqlave-go/onqlave/onqlaveconnection"
	"github.com/onqlavelabs/onqlave-go/onqlave/onqlavecredentials"
	"github.com/onqlavelabs/onqlave-go/onqlave/onqlaveencryption"
)

debugOption := onqlaveencryption.WithDebug(true) //This option lets you choose whether to start SDK operation in debug mode to info mode
arxOption := onqlaveencryption.WithArx("<arx_url>") //This is the Arx URL returned of the API Key created during setup. Keep in in a safe place.
credentialOption := onqlaveencryption.WithCredential(onqlavecredentials.Credential{
	AccessKey:  "<api_access_key>",   //This is the API Access Key returned of the API Key created during setup. Keep in in a safe place.
	SigningKey: "<api_signing_key>",  //This is the API Signing Key returned of the API Key created during setup. Keep in in a safe place.
	SecretKey:  "<api_secret_key>",   //This is the API Secret Key returned of the API Key created during setup. Keep in in a safe place.
})
retryOption := onqlaveencryption.WithRetry(onqlaveconnection.RetrySettings{
	Count:       <count>,         //Number of times to retry calling server endpoints in case of connection issue
	WaitTime:    <wait_time>,     //How long to wait between each retry
	MaxWaitTime: <max_wait_time>, //How long to wait in total for operation to finish
})

service := encryption.NewEncryption(debugOption, arxOption, credentialOption, retryOption)
defer service.Close()
```

**2. NodeJS**

```javascript
import { Encryption, withCredential, withRetry, withArx, Credential, RetrySettings }  from '@onqlavelabs/onqlave-node';
import { createReadStream, createWriteStream } from 'fs';

const arxOption = withArx("<arx_url>"); //This is the Arx URL returned of the API Key created during setup. Keep in in a safe place.
const apiKey = "<api_access_key>"       //This is the API Access Key returned of the API Key created during setup. Keep in in a safe place.
const signingKey = "<api_signing_key>"  //This is the API Signing Key returned of the API Key created during setup. Keep in in a safe place.
const secretKey = "<api_secret_key>"    //This is the API Secret Key returned of the API Key created during setup. Keep in in a safe place.
const credentialOption = withCredential(new Credential(apiKey, signingKey, secretKey));
const retryOption = withRetry(new RetrySettings(2, 400, 2000));

const service = new Encryption(arxOption, credentialOption, retryOption);
```
**3. Java**
```java
package com.example;

import com.onqlave.contract.Configuration;
import com.onqlave.contract.Credential;
import com.onqlave.contract.RetrySettings;
import com.onqlave.encryption.Encryption;

public class Main {
    public static void main(String[] agrs) {
        Credential credential = new Credential(
                "<api_access_key>",           //This is the API Access Key returned of the API Key created during setup. Keep in a safe place.
                "<api_signing_key>",          //This is the API Signing Key retruned of the API Key created during setup. Keep in a safe place.
                "<api_secret_key>");          //This is the API Secret Key retruned of the API Key created during setup. Keep in a safe place.
        RetrySettings retry = new RetrySettings(
                "<count>",                //Number of times to retry calling server endpoints in case of connection issue
                "<wait_time>",            //How long to wait between each retry
                "<max_wait_time>");        //How long to wait in total for operation to finis
        // Initial
        Encryption encryption = new Encryption(credential, retry, "<arx_url>", true);
    }
```

**4. Python**
```python
from onqlave.encryption import options
from onqlave.encryption.encryption import Encryption
from onqlave.credentials.credentials import Credential
from onqlave.connection.client import RetrySettings

cred_file_path = "credentials.json"

arx_option = options.ArxOption()
credential_option = Credential()

arx_option.load_arx_url_from_json(cred_file_path)
credential_option.load_config_from_json(cred_file_path)

retry_option = RetrySettings(count=1,wait_time=1,max_wait_time=2) 

encryption_engine = Encryption(
    debug_option=debug_option,
    arx_option=arx_option,
    credential_option=credential_option,
    retry_setting=retry_option
)
```

### Encrypt/Decrypt data

**1. Go**

```go
//Initialise the new encryption service using configurations as per [Usage]
service := encryption.NewEncryption(debugOption, arxOption, credentialOption, retryOption)
defer service.Close()

plainData := []byte("this data needs to be encrypted")
associatedData := []byte("this data needs to be authenticated, but not encrypted") //This can be an arbitrary piece of information you can use to for added security purpose.
cipherData, err := service.Encrypt(plainData, associatedData)
plainData, err := service.Decrypt(cipherData, associatedData)
```

**2. NodeJS**

```javascript
//Initialise the new encryption service using configurations as per [Usage]
const service = new Encryption(arxOption, credentialOption, retryOption);

const plainData = Buffer.from("This is the plain data");
const additionalData = Buffer.from("This is to authenticated not to encrypt"); //This can be an arbitrary piece of information you can use to for added security purpose.
const cipherData = await service.Encrypt(plainData, associatedData);
const plainData = await service.Decrypt(cipherData, associatedData);
```
**3. Java**
```java
    Encryption serivce = new Encryption(credential, retry, "<arx_url>", true);
    String plainText = "This is a plain text string";
    String associatedData = "this data needs to be authenticated, but not encrypted";
    byte[] cipherData = null;
    try {
        cipherData = serivce.Encrypt(plainText.getBytes(), associatedData.getBytes());
    } catch (Exception e) {
        //TODO: handle exception here.
        System.out.println(e.getMessage());
    }
    try {
        cipherData = serivce.Decrypt(plainText.getBytes(),associatedData.getBytes());
    } catch (Exception e) {
        //TODO: handle exception here.
        System.out.println(e.getMessage());
    }
```

**4. Python**
```python
plaintext = "hello world" # your data goes here
associated_data = "auth" # your authentication data goes here
cipher_text = encryption_engine.encrypt(plaintext.encode(), associated_data.encode())
decrypted_ciphertext = encryption_engine.decrypt(cipher_text,associated_data.encode())
```

### Encrypt/Decrypt stream

**1. Go**

```go
//Initialise the new encryption service using configurations as per [Usage]
service := encryption.NewEncryption(debugOption, arxOption, credentialOption, retryOption)
defer service.Close()

plainStream, _ := os.OpenFile("<file or network stream you are wishing to encrypt>", os.O_RDONLY, 0666)
associatedData := []byte("this data needs to be authenticated, but not encrypted") //This can be an arbitrary piece of information you can use to for added security purpose.
cipherStream,_ := os.OpenFile("<file or network stream you are whishing to stream the encrypted data to>", os.O_WRONLY, 0666)
err := service.EncryptStream(plainStream, cipherStream, associatedData)

plainStream,_ := os.OpenFile("<file or network stream you are whishing to stream the decrypted data to>", os.O_WRONLY, 0666)
err := service.DecryptStreamcipherStream, plainStream, associatedData)
```

**2. NodeJS**

```javascript

//Initialise the new encryption service using configurations as per [Usage]
const service = new Encryption(arxOption, credentialOption, retryOption);

const plainStream = createReadStream("<file or network stream you are wishing to encrypt>", { highWaterMark: 64 * 1024 });
const cipherStream = createWriteStream("<file or network stream you are whishing to stream the encrypted data to>", { encoding: 'binary' });
const associatedData = Buffer.from("this data needs to be authenticated, but not encrypted"); //This can be an arbitrary piece of information you can use to for added security purpose.
await service.encryptStream(plainStream, cipherStream, additionalData);

const plainStream = createWriteStream("<file or network stream you are whishing to stream the decrypted data to>", { highWaterMark: 64 * 1024 });
const associatedData = Buffer.from("this data needs to be authenticated, but not encrypted"); //This can be an arbitrary piece of information you can use to for added security purpose.
await service.decryptStream(cipherStream, plainStream, additionalData);
plainStream.close();
cipherStream.close();
```
**3. Java**
```java
    Encryption serivce = new Encryption(credential, retry, "<arx_url>", true);
    String plainText = "This is cipher data is already encrypted using `Encrypt` method";
    String associatedData = "this data needs to be authenticated, but not encrypted";
    InputStream encryptPlainStream = new ByteArrayInputStream(plainText.getBytes());
    ByteArrayOutputStream encryptCipherStream = new ByteArrayOutputStream();
    try {
        service.EncryptStream(encryptPlainStream, encryptCipherStream, associatedData.getBytes());
    } catch (Exception e) {
        //TODO: handle exception here.
        System.out.println(e.getMessage());
    }

    ByteArrayInputStream dataEncrypted = new ByteArrayInputStream(encryptCipherStream.toByteArray());
    ByteArrayOutputStream decryptPlainStream = new ByteArrayOutputStream();
    try {
        serivce.DecryptStream(dataEncrypted,decryptPlainStream, associatedData.getBytes());
    } catch (Exception e) {
        //TODO: handle exception here.
        System.out.println(e.getMessage());
    }
```

**4. Python**
```python
plain_file_stream = open("path to your plaintext file","rb")
plain_stream = io.BytesIO(plain_file_stream.read())
cipher_stream = io.BytesIO()
    
encryption_engine.encrypt_stream(plain_stream,cipher_stream,associated_data.encode())
cipher_stream.seek(0)

decrypted_stream = io.BytesIO()
encryption_engine.decrypt_stream(
    cipher_stream=cipher_stream,
    plain_stream=decrypted_stream,
    associated_data=associated_data.encode()
)
decrypted_stream.seek(0)

with open(
    "path to your decrypted file",
    "wb"
) as result:
    result.write(decrypted_stream.read())

```

## **What's next?**

🥐 Check out the [detail documentation](https://docs.onqlave.com/) to learn how our services work.

