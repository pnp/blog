---
title: "Run CLI for Microsoft 365 in Docker"
date: 2021-03-13T02:34:00-05:00
author: "Garry Trinder"
githubname: garrytrinder
categories: ["CLI for Microsoft 365"]
images:
- images/garrytrinder_0-1615630685864.png
tags: ["CLI for Microsoft 365"]
type: "regular"

---


We are delighted to announce that [CLI for Microsoft
365](https://aka.ms/cli-m365) Docker images are now available to
download and use from the Docker Hub.
If this doesn't mean a lot to you right now, then let me explain why we
feel this is a big deal.

Docker enables us to bundle a pre-configured version of CLI for
Microsoft 365 together with all its required dependencies into a
publicly downloadable image, which you can then use to create an
isolated environment on your local machine, called a
`container`, where you can use
the CLI for Microsoft 365 without cluttering your machine with
dependencies, and all performed by executing just a single command.
Sounds great, right? So how do you get started?
Firstly, you will need to have Docker installed and running on your host
machine, to do that, checkout the guides over in the Docker
[documentation](https://docs.docker.com/get-docker/), its free and can
be installed on any operating system. Once you have Docker running on
your machine, open up your command prompt of choice and run the below
command.

``` highlight
docker run --rm -it m365pnp/cli-microsoft365:latest
```

This command will instruct the Docker engine running on your host
machine to start a container using an image called
`m365pnp/cli-microsoft365`, as
the `:latest` tag is specified
we are also telling the engine to get the image which contains the
latest stable version of the CLI.
As the image won't exist on your host machine yet, Docker will
automatically download the image from the [Docker
Hub](https://hub.docker.com/r/m365pnp/cli-microsoft365), where our
images are publicly available, then start a new container which invoking
an interactive terminal session inside the container, this is determined
by the presence of the `-it`
switch in the `docker run`
command.

![garrytrinder_0-1615630685864.png](images/garrytrinder_0-1615630685864.png)

By default, the interactive terminal that is opened is a
`bash` shell, however if you
prefer using `PowerShell` then
thats fine, we have you covered as we also bundle
`PowerShell 7` as part of the
image.

If you want to use PowerShell, simply add `pwsh`{.language-plaintext
.highlighter-rouge} to the end of the `docker run`{.language-plaintext
.highlighter-rouge} command and you will get a PowerShell session
instead.

``` highlight
docker run --rm -it m365pnp/cli-microsoft365:latest pwsh
```

![garrytrinder_1-1615630685843.png](images/garrytrinder_1-1615630685843.png)

Now that you are at the interactive terminal, you can now invoke any CLI
for Microsoft 365 command using the `m365`{.language-plaintext
.highlighter-rouge}prefix as it is already installed, to help you, we
have even pre-configured tab command completion for you in both
`bash` and
`PowerShell`. Neat right.

![garrytrinder_2-1615630685839.png](images/garrytrinder_2-1615630685839.png)

When you are done with your session, just type
`exit` and your interactive
terminal will be closed and with that, the isolated container will also
be stopped and removed, freeing up resources on your host machine, this
is determined by the presence of the `--rm`{.language-plaintext
.highlighter-rouge} switch in the `docker run`{.language-plaintext
.highlighter-rouge} command.

![garrytrinder_3-1615630685863.png](images/garrytrinder_3-1615630685863.png)

This doesn't mean that the image you just downloaded has been removed as
well, this remains on your machine, we just removed the container
instance that was started, so when you run the
`docker run` command again, this
time you won't need to download the image and just head straight for the
interactive terminal.
As the container is removed after exiting the interactive terminal,
everything stored in the container is removed, this includes any
authentication information, therefore when you start a new container you
will need to re-authenticate with Microsoft 365.
Checkout our
[guide](https://pnp.github.io/cli-microsoft365/user-guide/run-cli-in-docker-container/)
for more details on how to use these images, including how to get the
latest beta releases, update existing images, execute scripts stored on
your local machine inside the running container and how to use your own
Azure AD identity for connecting to Microsoft 365 from the running
container.
We also demonstrated how to run CLI for Microsoft 365 in Docker
container in the General Microsoft 365 Development Special Interest
Group (SIG) - Bi-weekly sync call recorded on February 18, 2021.

We will be releasing new beta and stable versions as part of our regular
release cadence, so you will be able to use the new version of the CLI
for Microsoft 365 in Docker immediately after our release to
`npm`.
For a list of available tags, checkout the
[m365pnp/cli-microsoft365](https://hub.docker.com/r/m365pnp/cli-microsoft365)
repository on Docker Hub for the latest images.
