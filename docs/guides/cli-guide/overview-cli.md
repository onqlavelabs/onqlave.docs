At the moment there is only one way to use the CLI via the provided docker container.

## **Before you start**

Make sure that you have <mark>[an executable docker](https://www.docker.com/)</mark> on your machine.

In addition, you can try to <mark>[get comfortable with docker](https://docs.docker.com/)</mark> before starting.

## **Get the container**

Use this command to get our docker image:

```
docker pull australia-southeast1-docker.pkg.dev/temp-control-plane/onqlave/onqlavelabs/onqlave.all:{$cli-version}
```

Replace **{$cli-version}** with your preferred version. We always recommend the latest version. You can check out <mark>[the list of our releases here](https://github.com/onqlavelabs/onqlave.all/releases)</mark> for an exact version number.

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
  apps        applications management
  arx         arx management
  auth        authentication
  completion  Generate the autocompletion script for the specified shell
  configs     configs environment variables
  help        Help about any command
  keys        api keys management
  tenants     tenants management
  users       users management

Flags:
  -h, --help      help for onqlave
      --json      Output logs as JSON.  Set to true if stdout is not a TTY.
  -v, --version   version for onqlave

Use "onqlave [command] --help" for more information about a command.

```

## **Init the configuration**

```
# onqlave configs init
```

If the initialization is success, the terminal will look like this

```
If the configurations was inited successfully, there should be a output like following
🎉 Done!  You successfully initialize your environment . Next step is to signup/login is you already haven't.                                                                                                             
For more information, read our documentation at https://www.onqlave.com/docs 
```

## **Explore the help for each command**

In the CLI, you can try this formula to get help about all provided commands:

```
# onqlave help {your_want_to_know_command}
```

You may select **{your_want_to_know_command}** from this list

```
Available Commands:
  apps        applications management
  arx         arx management
  auth        authentication
  completion  Generate the autocompletion script for the specified shell
  configs     configs environment variables
  help        Help about any command
  keys        api keys management
  tenants     tenants management
  users       users management

```

## **Looking for another way of interaction ?**

If this is not your preffered way, considering [the Graphical Web Interface here](../web-app-guide/overview-gui.md)