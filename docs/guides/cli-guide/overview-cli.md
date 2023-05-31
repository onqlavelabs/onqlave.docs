Currently, there is only one way to use the CLI. This is via the provided docker container.

## **Before you start**

Make sure that you have an <u>**[executable docker](https://www.docker.com/)**</u> on your machine.

In addition, you can try to get comfortable with docker before proceeding by reviewing <u>**[the docker documentation](https://docs.docker.com/)**</u>

## **Get the container**

Use this command to get our latest docker image:

```
docker pull ghcr.io/onqlavelabs/onqlavelabs/onqlave.all:latest
```
<!--
Replace **{$cli-version}** with your preferred version. We always recommend the latest version. You can check out <mark>[the list of our releases here](https://github.com/onqlavelabs/onqlave.all/pkgs/container/onqlavelabs%2Fonqlave.all)</mark> for an exact version number. -->

## **Launch the container**

Use this command to run the image:

```
docker run -it {$image-id} bash
```

After entering the container via BASH shell, you can try to type this command to make sure everything works:

```
# onqlave
```

The output should look like this:

```
Usage:
 onqlave [command]

Examples:
onqlave

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

## **Init the configuration**

```
# onqlave config init
```

If the configuration initialization is a success, you will see the following in the terminal

```
🎉 Done!  You successfully initialize your environment . Next step is to signup/login if you already haven't.
For more information, read our documentation at https://docs.onqlave.com
```

## **Explore the help for each command**

In the CLI, you can try this formula to get specific help about each of the available commands:

```
# onqlave help {arx}
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
