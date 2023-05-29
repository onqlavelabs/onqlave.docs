Before starting the authentication process via CLI, please make sure that you have a valid account and valid tenant name.

## **Authenticating**
The authentication process will go through 4 steps:

### **1. Input authentication information via CLI:**

Use this command to begin the authn process:

```
# onqlave auth login your_email_account@domain.com -t your-verified-tenant-name
```

After entering the above command, the output should appear as follows:
```
Login instruction is sent to email address 'your_email_count@domain.com'.
Please be mindful that the link provided in email is only valid for 30 minutes.
```

### **2. Wait for an email from Onqlave**

You should shortly receive an email at the address you provided (in the previous step).

Please note that the link contained within the email is only valid for 30 minutes.

### **3. Confirm your email**
Open your email and click on the provided link to complete the email confirmation prompt
![Email confirmation](https://t36712295.p.clickup-attachments.com/t36712295/629391bb-7432-442c-9dd0-f24f91cbae7b/image.png)

### **4. Return to the CLI and work with an authenticated session**
After confirming your email, the CLI output should look like this:
```
🎉 Done!  You successfully login to Onqlave platform.

For more information, read our documentation at https://docs.onqlave.com

```

From here you can explore the interaction options provided by onqlave-cli using one of the following commands:

```plain
# onqlave
```

or

```plain
# onqlave help
```

or

```plain
# onqlave --help
```

Each will produce instructions for the supported commands of onqlave-cli:

```plain
Usage:
  onqlave [command]

Examples:
onqlave

Available Commands:
  application application management
  arx         arx management
  auth        authentication
  completion  Generate the autocompletion script for the specified shell
  config      config environment variables
  help        Help about any command
  key         api key management
  tenant      tenant management
  user        user management

Flags:
  -h, --help      help for onqlave
      --json      JSON Output. Set to true if stdout is not a TTY.
  -v, --version   version for onqlave

Use "onqlave [command] --help" for more information about a command


```
