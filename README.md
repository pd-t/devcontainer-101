# Devcontainer 101

This is the repository for the PyConDE 2024 talk "Unlock the Power of Dev Containers: Build a Consistent Python Development Environment in Seconds!". The slides of the talk can be found [here](docs/pycon_2024.pdf).

## Why should you use DevContainers?
If you want a reproducible development environment in Python that is easy to set up, then DevContainers are a good choice, if not the best. DevContainer allows you to define the operating system and system libraries next to the Python packages and the Python interpreter. All together this results in an always robust, reproducible development environment.

## How to use DevContainers?
DevContainers are now supported by a large number of IDEs, which means next to VSCode also PyCharm and Nvim, for example. Furthermore, next to Github, more and more remote development platforms support DevContainers. The prerequisite is that [docker](https://docs.docker.com/engine/install/) is installed on the computer.

## Wo kann ich mehr zum Thema DevContainer lernen?
A wonderful source of inspiration can be found in the [VSCode DevContainer documentation](https://code.visualstudio.com/docs/remote/containers). The DevContainer specification can be viewed [here](https://containers.dev/).

## Wie kann ich DevContainer in meinem Projekt nutzen?
In this repository you will find an example of how you can use DevContainer in your project. All you have to do is copy the file `.devcontainer/devcontainer.json` into your project and adapt the file `.devcontainer/Dockerfile`. You can then start the development environment by clicking on the green icon in the bottom left-hand corner of VSCode.

If you are interested in more complex setups, we recommend the following repositories:

- [Devcontainer Pytorch Example](https://github.com/pd-t/devcontainer-pytorch-template)
- [Devcontainer S3 Example](https://github.com/pd-t/s3-devcontainer)
- [DevContainer Docker Example](https://github.com/pd-t/docker-devcontainer-template)

## Tips and Tricks
There is an issue installing vscode extensions using MacOS (https://github.com/microsoft/vscode/issues/173327). In case you use MacOS please be sure to uncomment the following line in the `.devcontainer.json` file:

```json
    "extensions.verifySignature": false
```

MacOS users can also use native x86_64 images very well using [Rosetta](https://www.docker.com/blog/docker-desktop-4-25/). If you want to explicitly use an x86_64 image, you have to add the following line to the `.devcontainer.json` file:

```json
    "runArgs": ["--platform", "linux/amd64"],
```