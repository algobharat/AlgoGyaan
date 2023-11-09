# Install

## Prerequisites

The key required dependency is Python 3.10+, but some of the installation options below will install that for you.

AlgoKit also has some runtime dependencies that also need to be available for particular commands.

> **Note**
> You can still install and use AlgoKit without these dependencies and AlgoKit will tell you if you are missing one for a given command.

- Git - Git is used when creating and updating projects from templates
- Docker - Docker Compose (and by association, Docker) is used to run the AlgoKit LocalNet environment, we require Docker Compose 2.5.0+

## Cross-platform installation

AlgoKit can be installed using OS specific package managers, or using the python tool [pipx](https://pypa.github.io/pipx/) see below for specific installation instructions.

- [Windows](#install-algokit-on-windows)
- [Mac](#install-algokit-on-mac)
- [Linux](#install-algokit-on-linux)
- [pipx](#install-algokit-with-pipx-on-any-os)

## Install AlgoKit on Windows

> **Note**
> This method will install the most recent python3 version [via winget](https://learn.microsoft.com/en-us/windows/package-manager/winget/). If you already have python 3.10+ installed, you may [prefer to use pipx directly instead](#install-algokit-with-pipx-on-any-os) so you can control the python version used.

1. Ensure prerequisites are installed

   - [Git](https://github.com/git-guides/install-git#install-git-on-windows) (or `winget install git.git`)
   - [Docker](https://docs.docker.com/desktop/install/windows-install/) (or `winget install docker.dockerdesktop`)
     > **Note**
     > See [our LocalNet documentation](https://github.com/algorandfoundation/algokit-cli/blob/main/docs/features/localnet.md#prerequisites) for more tips on installing Docker on Windows

2. Install using WinGet

   1. Install python: `winget install python.python.3.11`
   2. Restart the terminal to ensure Python and pip are available on the path

      > **Note**
      > Windows has a feature called **App Execution Aliases** that provides redirects for the Python command that guide users to the
      > Windows Store. Unfortunately these aliases can prevent normal execution of Python if Python is installed via other means, to disable them
      > search for **Manage app execution aliases** from the start menu, and then turn off entries listed as
      > **App Installer python.exe** or **App Installer python3.exe**.

   3. Install pipx:
      ```
      pip install --user pipx
      python -m pipx ensurepath
      ```
   4. Restart the terminal to ensure pipx is available on the path
   5. Install AlgoKit via pipx: `pipx install algokit`
   6. Restart the terminal to ensure AlgoKit is available on the path

3. [Verify installation](#verify-installation)
