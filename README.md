# Workhard Dev Workspace

## Pre-requisite

### Install Task

[details](https://taskfile.dev/#/installation?id=package-managers)

```.shell
# for macOS
brew install go-task/tap/go-task

# for Snap users
sudo snap install task --classic

# for Scoop users
scoop bucket add extras
scoop install task

# for AUR
yay -S taskfile-git
```

## Setup

1. Pull workspace git repository
    ```shell
    git clone https://github.com/workhard-finance/workspace
    ```
1. Pull submodules
    ```
    task pull
    ```
1. Install dependencies
    ```
    task install
    ```