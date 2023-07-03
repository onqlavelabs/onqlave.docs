Currently, there is only one way to use the CLI. This is via the provided docker container.

## **Before you start**

Make sure that you have an <u>**[executable docker](https://www.docker.com/)**</u> on your machine.

In addition, you can try to get comfortable with docker before proceeding by reviewing <u>**[the docker documentation](https://docs.docker.com/)**</u>

## **Check the quick start video guide**

<div style="width:100%;height:0px;position:relative;padding-bottom:56.250%;"><iframe src="https://streamable.com/e/30jkhw" frameborder="0" width="100%" height="100%" allowfullscreen style="width:100%;height:100%;position:absolute;left:0px;top:0px;overflow:hidden;"></iframe></div>

## **Download Onqlave CLI**

### **Linux**

- Download Linux executable file `onqlave-linux` from the release assets
- Grant executable permission to `onqlave-linux` file

```
sudo chmod +x onqlave-linux
```

- Make sure `onqlave-linux` is executable:

```
./onqlave-linux
```

### **MacOS**

- Download Linux executable file `onqlave-darwin` from the release assets
- Grant executable permission to `onqlave-darwin` file

```
sudo chmod +x onqlave-darwin
```

- Make sure `onqlave-darwin` is executable:

```
./onqlave-darwin
```

### **Windows**

- Download Windows executable file `onqlave-windows.exe` from the release assets
- Make sure `onqlave-windows.exe` is executable:

```
.\onqlave-windows.exe
```

### **Docker**

- Download the Docker image from the CLI release note

```
docker pull ghcr.io/onqlavelabs/onqlavelabs/onqlave.cli:{$version}
```

- Verify the Docker image

```
docker images
```

The Docker image for the CLI package should be visible in the Docker images list:

```
REPOSITORY                                   TAG         IMAGE ID       CREATED         
ghcr.io/onqlavelabs/onqlavelabs/onqlave.cli  {$version}  17a828917e85   45 hours ago
```

- Run the Docker image in interactive mode

```
docker run -it 17a828917e85
```

- Make sure `onqlave` CLI package inside the docker image is executable:

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
  installation script; Or you can download the CLI executable directly from the release.

## **Init the configuration**

```
onqlave config init
```

If the configuration initialization is a success, you will see the following in the terminal

```
🎉 Done!  You successfully initialize your environment . Next step is to signup/login if you already haven't.
For more information, read our documentation at https://docs.onqlave.com
```

## **Signup/login**

After init the configuration, you can use this command to signup:

```
onqlave auth signup your_email@domain.com --full_name="You Full Name" --tenant_name="Your tenant name"
```

Then you will receive and email from our communications service at <comms@onqlave.com> with an activation link to complete the signup process. Just follow the link and confirm your registered email with us. Then you will be ready to proceed to the login step:

```
onqlave auth login your_email@domain.com --tenant_name="Your tenant name"
```

You will also receive another email from <comms@onqlave.com> with a login link. After you complete the login verification process. You will be able to interact with the Onqlave platform via CLI.

## **Explore the help for each command**

In the CLI, you can try this formula to get specific help about each of the available commands:

```
onqlave help {arx}
```

You may replace {arx} with other commands listed below to get the help.

```
Available Commands:
 application application management
 arx         arx management
 auth        authentication
 completion  Generate the auto completion script for the specified shell
 config      config environment variables
 help        Help about any command
 key         api key management
 tenant      tenant management
 user        user management

Flags:
 -h, --help      help for onqlave
     --json      JSON Output. Set to true if stdout is not a TTY.
 -v, --version   version for onqlave

Use "onqlave [command] --help" for more information about a command.
```


## **Looking for another form of interaction?**

If this is not your preferred way to interact with Onqlave, consider using the **[the Graphical Web Interface](../web-app-guide/overview-gui.md)**
