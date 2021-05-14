# Workhard Dev Workspace

## Pre-requisite

### Install `task`

```.shell
# for macOS
brew install go-task/tap/go-task

# for Snap users
sudo snap install task --classic

# Or please visit the here; https://taskfile.dev/#/installation?id=package-managers
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

## Test protocol

```.shell
task test
```

## Run

a) You can simply start dev server by running

```.shell
task develop
```

b) Or if you want to see the log output separately, prepare 3 terminal windows(or tabs) and then
1. Run localhost node
    ```.shell
    # terminal 1
    task localhost:node
    ```
1. Deploy contracts to the local hardhat node
    ```.shell
    # terminal 2
    task localhost:deploy
    ```
1. Run frontend
    ```.shell
    # terminal 3
    task frontend -- start
    ```

## Develop

1. Please install vscode [here](https://code.visualstudio.com/download).
2. Open vscode and select "File > Open Workspace...".
3. Then open "workhard.code-workspace" config file.
4. Enjoy dev :)

## Contribution
Workhard is using git submodule system

1. Contracts
    1. Go to 'protocol' directory and make changes.
    2. In 'protocol' directory, commit your changes.
    3. Push your commits to your forked protocol repository.
    4. Make PR to https://github.com/workhard-finance/protocol 

2. Frontend app
    1. Go to 'frontend-v1' directory and make changes.
    2. In 'frontend-v1' directory, commit your changes.
    3. Push your commits to your forked fronend repository.
    4. Make PR to https://github.com/workhard-finance/fronend-v1

3. Apply changes to workspace

    1. Now you'll have uncommitted changes in the root workspace directory.
    2. Commit the updated commit hashes of the submodules.
    3. Push the updated workspace to your own forked workspace repository.
    4. Make PR to https://github.com/workhard-finance/workspace

