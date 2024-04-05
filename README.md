# devcontainer-hello

Learning about Development Containers

> This requires to have the [Docker](https://www.docker.com/) on your machine.

- [Development Containers](https://containers.dev/)

- [[GitHub Org] devcontainers](https://github.com/devcontainers)

  - [[GitHub] devcontainers/spec](https://github.com/devcontainers/spec) - Development Containers: Use a container as a full-featured development environment.

  - [[GitHub] devcontainers/templates](https://github.com/devcontainers/templates) - Repository for Dev Container Templates that are managed by Dev Container spec maintainers.

  - [[GitHub] devcontainers/images](https://github.com/devcontainers/images) - Repository for pre-built dev container images published under mcr.microsoft.com/devcontainers.

## Learning

- [Use a Docker container as a development environment with Visual Studio Code - Training | Microsoft Learn](https://learn.microsoft.com/en-us/training/modules/use-docker-container-dev-env-vs-code/)

- [[YouTube Playlist] Dev Containers Overview | Visual Studio Code](https://www.youtube.com/playlist?list=PLj6YeMhvp2S7FFvNDj7ks7ndm0u69Ufrs)

  - [[YouTube] Get Started with Dev Containers in VS Code | Visual Studio Code](https://www.youtube.com/watch?v=b1RavPr_878) (2023/09/05)

    - [[GitHub] microsoft/vscode-remote-try-python](https://github.com/microsoft/vscode-remote-try-python) - Python sample project for trying out Dev Containers

    - [Developing inside a Container using Visual Studio Code Remote Development | Visual Studio Code Docs](https://code.visualstudio.com/docs/devcontainers/containers)

    - [Dev Containers tutorial | Visual Studio Code Docs](https://code.visualstudio.com/docs/devcontainers/tutorial)

  - [[YouTube] Different Ways to Run Dev Containers: VS Code vs CLI | Visual Studio Code](https://www.youtube.com/watch?v=Fc6TAahZ1Pk) (2023/10/04)

  - [[YouTube] Dev Container Features & Lifecycle Hooks | Visual Studio Code](https://www.youtube.com/watch?v=iCopdmuabBM) (2024/02/28)

- [[YouTube] Working with Dev Containers by Chris Ayers | Devoxx](https://www.youtube.com/watch?v=HV7LJ_LUZ5A) (2023/05/16)

- [[YouTube] If you're not developing with this, you're wasting your time | Articulated Robotics](https://www.youtube.com/watch?v=dihfA7Ol6Mw) (2024/01/05)

- [[YouTube] My Favorite Way To Handle Dev Environments - VS Code Devcontainers | DanCanCode](https://www.youtube.com/watch?v=SDa3v4Quj7Y) (2023/01/12)

- [[YouTube] How To Set Up Local DevOps Environment With Docker using Dev Containers | Chandra Shettigar](https://www.youtube.com/watch?v=XTfIVffnapo) (2023/11/15)

  - [DevOps Local Setup: Docker & Dev-Containers in VSCode | Devteds](https://www.devteds.com/devops-local-setup-with-docker-and-devcontainers-vscode/)

  - [[GitHub] devteds/devops-local-setup-docker-devcontainer-vscode](https://github.com/devteds/devops-local-setup-docker-devcontainer-vscode)

- [[YouTube] How to build your first Devcontainer | GitHub](https://www.youtube.com/watch?v=C_5tDWsWSj0) (2024/03/19)

  - [[GitHub] diagrid-labs/dapr-workflow-demos](https://github.com/diagrid-labs/dapr-workflow-demos)

- [Using Devcontainers for Local Development | xMatters](https://www.xmatters.com/blog/an-introduction-to-using-devcontainers-for-local-development) (2021/05/31)

- [Getting Started with Dev Containers | JosephGuadagno.net](https://www.josephguadagno.net/2022/12/10/getting-started-with-developer-containers) (2022/12/10)


### Advanced container configuration

- [Advanced container configuration | Visual Studio Code](https://code.visualstudio.com/remote/advancedcontainers/overview)

  - [Environment variables](https://code.visualstudio.com/remote/advancedcontainers/environment-variables)

  - [Change the default source code mount](https://code.visualstudio.com/remote/advancedcontainers/change-default-source-mount)

  - [Connect to multiple containers](https://code.visualstudio.com/remote/advancedcontainers/connect-multiple-containers)

  - [Configure separate containers](https://code.visualstudio.com/remote/advancedcontainers/configure-separate-containers)


#### Using Docker Compose

- [[YouTube] Customize Dev Containers in VS Code with Dockerfiles and Docker Compose | Visual Studio Code](https://www.youtube.com/watch?v=p9L7YFqHGk4) (2024/01/31)

- [[YouTube] Working with Multiple Dev Containers in VS Code | Visual Studio Code](https://www.youtube.com/watch?v=bVmczgfeR5Y) (2023/11/30)

  - [[GitHub] madebygps/multiple-dev-container-vscode](https://github.com/madebygps/multiple-dev-container-vscode) - An example repo on how to use multiple devcontainer.json files with VS Code.

## Tips

- [Dev Containers Tips and Tricks | Visual Studio Code](https://code.visualstudio.com/docs/devcontainers/tips-and-tricks)

- [Sharing Git credentials with your container | Visual Studio Code](https://code.visualstudio.com/remote/advancedcontainers/sharing-git-credentials)

### MacOS - passing the ssh credentions to inside of the devcontainer

> If you get and issue while trying to commit your changes from inside of the devcontainer, the solution that I took on my case

1. Make sure to have your ssh key for the git host mapped like the following example


```bash
# ~/.ssh/config

Host *
  ForwardAgent yes

Host github.com
  HostName github.com
  User git
  IdentityFile ~/.ssh/{private_ssh_key}
  AddKeysToAgent yes
```

2. On your `devconfig.json` file, add the following mount configuration

```json
...

  "mounts": [
    "type=bind,source=${localEnv:HOME}/.ssh,target=/home/vscode/.ssh,readonly"
  ]

...
```


## Projects that uses Development Containers

- [[GitHub] home-assistant/core](https://github.com/home-assistant/core) - Open source home automation that puts local control and privacy first.

## Tools

- [Supporting tools and services | Development Containers](https://containers.dev/supporting)

- [[GitHub] esensar/nvim-dev-container](https://github.com/esensar/nvim-dev-container)

### CLI

- [[GitHub] devcontainers/cli](https://github.com/devcontainers/cli) - A reference implementation for the specification that can create and configure a dev container from a `devcontainer.json`.

## DevPod

- [DevPod](https://devpod.sh/) - Open Source Dev-Environments-As-Code

- [[GitHub] loft-sh/devpod](https://github.com/loft-sh/devpod) - Codespaces but open-source, client-only and unopinionated: Works with any IDE and lets you use any cloud, kubernetes or just localhost docker.

- [[YouTube] Introducing DevPod - Codespaces but Open Source | Loft Labs](https://www.youtube.com/watch?v=87oHtFO5lkc) (2023/05/16)

  - [Introducing DevPod - Codespaces but Open Source | Loft Blog](https://loft.sh/blog/introducing-devpod-codespaces-but-open-source/) - DevPod does not host or manage the dev environments. Instead, DevPod introduces a way to define a dev environment which can then be run in any cloud infrastructure or even on a localhost machine using Docker or Kubernetes.

- [[YouTube] Running Dev Containers with DevPod | Containers from the Couch](https://www.youtube.com/watch?v=pV2ymHluPtE) (2023/06/27)

- [[YouTube] Open Source Dev Containers with DevPod | Cloud Native Rejekts](https://www.youtube.com/watch?v=jSVWiecTeo0) (2023/12/07)

- [[YouTube] Open Source Dev Containers for macOS with Colima and DevPod | Loft Labs](https://www.youtube.com/watch?v=7oxLnYT6p_w) (2023/11/23)

  - [Open Source Dev Containers for macOS with Colima and DevPod | Loft Blog](https://loft.sh/blog/dev-containers-with-colima-and-devpod/)

  - [[GitHub] abiosoft/colima](https://github.com/abiosoft/colima) - Container runtimes on macOS (and Linux) with minimal setup

### Visual Studio Code Extensions

- [Dev Containers extension](https://marketplace.visualstudio.com/items?itemName=ms-vscode-remote.remote-containers) - Open any folder or repository inside a Docker container and take advantage of Visual Studio Code's full feature set.

  - [Customizing the VS Code Extensions](https://containers.dev/supporting#visual-studio-code)

- [Remote Development extension pack](https://marketplace.visualstudio.com/items?itemName=ms-vscode-remote.vscode-remote-extensionpack) - An extension pack that lets you open any folder in a container, on a remote machine, or in WSL and take advantage of VS Code's full feature set.

### IntelliJ IDEA

- [IntelliJ IDEA 2023.2 EAP 6: AI Assistant, Dev Containers Support, and More | The IntelliJ IDEA Blog](https://blog.jetbrains.com/idea/2023/06/intellij-idea-2023-2-eap-6/#support-for-dev-containers)

- [Dev Containers | WebStorm Documentation](https://www.jetbrains.com/help/webstorm/connect-to-devcontainer.html)

### CodeSandbox

- [Dev Containers | CodeSandbox Docs](https://codesandbox.io/docs/learn/environment/devcontainers)
