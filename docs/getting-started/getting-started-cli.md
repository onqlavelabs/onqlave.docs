
## **What does the CLI of Onqlave Platform do?**

The Command Line Interface (CLI) of Onqlave Platform provide a developer-friendly interface
to perform the [same interactions as the GUI](../getting-started-gui)

## **How can I use the CLI ?**

At this moment, you can use CLI via a docker container.

1. Get the Docker image:

```
docker pull australia-southeast1-docker.pkg.dev/temp-control-plane/onqlave/onqlavelabs/onqlave.all:{$cli-version}
```

Replace the {$cli-version} with your desired one

2. Run the docker image in interactive mode

```
docker run -it {$image-id} bash
```

Replace the {$image-id} with your downloaded image in the first step