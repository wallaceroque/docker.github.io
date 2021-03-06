---
description: Set up the application
keywords: Python, application, setup
redirect_from:
- /docker-cloud/getting-started/python/2_set_up/
- /docker-cloud/getting-started/golang/2_set_up/
title: Set up your environment
---

In this step you install the Docker Cloud CLI so interact with the service using your command shell. This tutorial uses CLI commands to complete actions.

## Install the Docker Cloud CLI

Install the docker-cloud CLI using the package manager for your system.

#### Install using a Docker container

If you have Docker Engine installed locally, you can simply run the following command regardless of which operating system you are using.

```
docker run dockercloud/cli -h
```

This runs a container that installs the docker-cloud CLI for you. Learn more about this container [here](https://github.com/docker/dockercloud-cli#docker-image).

#### Install for Linux or Windows

Open your shell or terminal application and execute the following command:

```bash
$ pip install docker-cloud
```

#### Install on macOS

We recommend installing Docker CLI for macOS using Homebrew. If you don't have `brew` installed, follow the instructions here: <a href="http://brew.sh" target="_blank">http://brew.sh</a>

Once Homebrew is installed, open Terminal and run the following command:

```bash
$ brew install docker-cloud
```

## Validate the CLI installation
Check that the CLI installed correctly, using the `docker-cloud -v` command. (This command is the same for every platform.)

```bash
$ docker-cloud -v
docker-cloud 1.0.0
```

You can now use the `docker-cloud` CLI commands from your shell.

The documentation for the Docker Cloud CLI tool and API [here](/apidocs/docker-cloud.md).


## Log in

Use the `login` CLI command to log in to Docker Cloud. Use the username and password you used when creating your Docker ID. If you use Docker Hub, you can use the same username and password you use to log in to Docker Hub.

```
$ docker login
Username: my-username
Password:
Login succeeded!
```

You must log in to continue this tutorial.

## Set your username as an environment variable

For simplicity in this tutorial, we use an environment variable for your Docker Cloud username. If you will be copying and pasting the tutorial commands, set the environment variable using the command below. (Change `my-username` to your username.)

If you don't want to do this, make sure you substitute your username for $DOCKER_ID_USER whenever you see it in the example commands.

```none
$ export DOCKER_ID_USER=my-username
```

**If you are running the tutorial with an organization's resources:**

By default, the `docker-cloud` CLI uses your default user namespace, meaning the
repositories, nodes, and services associated with your individual Docker ID
account name. To use the CLI to interact with objects that belong to an
[organization](../../orgs.md), prefix these commands with
`DOCKERCLOUD_NAMESPACE=my-organization`, or set this variable as in the example below.

```none
$ export `DOCKERCLOUD_NAMESPACE=my-organization`
```


 See the [CLI documentation](../../installing-cli.md#use-the-docker-cloud-cli-with-an-organization) for more information.


Next up, we'll [Prepare the app](3_prepare_the_app.md).
