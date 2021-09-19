# My Dapp

This project is for the blockchain application My Dapp. It contains code for the Smart Contract, web-based dapp and NodeJS server. 

# Pre-requisites

In order to develop and build "My Dapp," the following pre-requisites must be installed:

* [Visual Studio Code](https://code.visualstudio.com/download) (or any IDE for editing Javascript)
* [NodeJS](https://nodejs.org/en/download/)
* [Yarn](https://classic.yarnpkg.com/en/docs/install) (DappStarter uses [Yarn Workspaces](https://classic.yarnpkg.com/en/docs/workspaces))
* [Solana CLI Tools](https://docs.solana.com/cli/install-solana-cli-tools)
* Rust (see "Dependency Guides" at the end for help installing) 
### Dependency Checklist 
```bash
$ node --version
$ npm --version
$ rustup --version
$ rustc --version
$ cargo --version
$ solana --version
```

### Windows Users

Before you proceed with installation, it's important to note that many blockchain libraries either don't work or generate errors on Windows. If you try installation and can't get the startup scripts to completion, this may be the problem. In that case, it's best to install and run DappStarter using Windows Subsystem for Linux (WSL). Here's a [guide to help you install WSL](https://docs.decentology.com/guides/windows-subsystem-for-linux-wsl).

Blockchains known to require WSL: Solana
# Installation

Using a terminal (or command prompt), change to the folder containing the project files and type: `yarn` This will fetch all required dependencies. The process will take 1-3 minutes and while it is in progress you can move on to the next step.

# Yarn Errors

You might see failures related to the `node-gyp` package when Yarn installs dependencies.
These failures occur because the node-gyp package requires certain additional build tools
to be installed on your computer. Follow the [instructions](https://www.npmjs.com/package/node-gyp) for adding build tools and then try running `yarn` again.

# Build, Deploy and Test
Using a terminal (or command prompt), change to the folder containing the project files and type: `yarn start` This will run all the dev scripts in each project package.json.

The first time you run `yarn start` there are a fair number of Rust libraries that are
downloaded and pre-compiled. As a result, it may be take from 5-10 mins. before the
dapp is compiled and launched the first time. On subsequent compilations, the build
time will only be a few seconds.

## File Locations
Here are the locations of some important files:
* Program Code: [packages/dapplib/programs/src/lib.rs](packages/dapplib/programs/src/lib.rs)
* Dapp Library: [packages/dapplib/src/dapp-lib.js](packages/dapplib/src/dapp-lib.js)
* Solana Wrapper: [packages/dapplib/src/solana.js](packages/dapplib/src/solana.js) 
* Blockchain Interactions: [packages/dapplib/src/blockchain.js](packages/dapplib/src/blockchain.js)
* Data Layouts: [packages/dapplib/src/scripts/layouts.js](packages/dapplib/src/scripts/layouts.js)
* Deploy Script: [packages/dapplib/src/scripts/deploy.js](packages/dapplib/src/scripts/deploy.js)


To view your dapp, open your browser to http://localhost:5000 for the DappStarter Workspace.

We ♥️ developers and want you to have an awesome experience. You should be experiencing Dappiness at this point. If not, let us know and we will help. Join our [Discord](https://discord.gg/XdtJfu8W) or hit us up on Twitter [@Decentology](https://twitter.com/decentology).

## Dependency Guides

This section contains installation guides for common dev environments. 

### Rust

(Source: Solana)
We suggest that you install Rust using the 'rustup' tool. Rustup will install
the latest version of Rust, Cargo, and the other binaries.

Follow the instructions at [Installing Rust](https://www.rust-lang.org/tools/install).

For Mac users, Homebrew is also an option.  The Mac Homebrew command is `brew install rustup` and then
`rustup-init`. See [Mac Setup](https://sourabhbajaj.com/mac-setup/Rust/) &
[Installing Rust](https://www.rust-lang.org/tools/install) for more details.

After installation, you should have `rustc`, `cargo`, & `rustup`. You should
also have `~/.cargo/bin` in your PATH environment variable.

# Try Out Development Containers: Rust

A **development container** is a running [Docker](https://www.docker.com) container with a well-defined tool/runtime stack and its prerequisites. You can try out development containers with **[GitHub Codespaces](https://github.com/features/codespaces)** or **[Visual Studio Code Remote - Containers](https://aka.ms/vscode-remote/containers)**.

This is a sample project that lets you try out either option in a few easy steps. We have a variety of other [vscode-remote-try-*](https://github.com/search?q=org%3Amicrosoft+vscode-remote-try-&type=Repositories) sample projects, too.

> **Note:** If you already have a Codespace or dev container, you can jump to the [Things to try](#things-to-try) section.

## Setting up the development container

### GitHub Codespaces
Follow these steps to open this sample in a Codespace:
1. Click the Code drop-down menu and select the **Open with Codespaces** option.
1. Select **+ New codespace** at the bottom on the pane.

For more info, check out the [GitHub documentation](https://docs.github.com/en/free-pro-team@latest/github/developing-online-with-codespaces/creating-a-codespace#creating-a-codespace).

### VS Code Remote - Containers
Follow these steps to open this sample in a container using the VS Code Remote - Containers extension:

1. If this is your first time using a development container, please ensure your system meets the pre-reqs (i.e. have Docker installed) in the [getting started steps](https://aka.ms/vscode-remote/containers/getting-started).

2. To use this repository, you can either open the repository in an isolated Docker volume:

    - Press <kbd>F1</kbd> and select the **Remote-Containers: Try a Sample...** command.
    - Choose the "Rust" sample, wait for the container to start, and try things out!
        > **Note:** Under the hood, this will use the **Remote-Containers: Clone Repository in Container Volume...** command to clone the source code in a Docker volume instead of the local filesystem. [Volumes](https://docs.docker.com/storage/volumes/) are the preferred mechanism for persisting container data.

   Or open a locally cloned copy of the code:

   - Clone this repository to your local filesystem.
   - Press <kbd>F1</kbd> and select the **Remote-Containers: Open Folder in Container...** command.
   - Select the cloned copy of this folder, wait for the container to start, and try things out!

## Things to try

Once you have this sample opened, you'll be able to work with it like you would locally.

> **Note:** This container runs as a non-root user with sudo access by default. Comment out `"remoteUser": "vscode"` in `.devcontainer/devcontainer.json` if you'd prefer to run as root.

Some things to try:

1. **Edit:**
   - Open `main.rs`
   - Try adding some code and check out the language features.
   - Notice that several extensions are already installed in the container, such as Rust support for VS Code, since the `.devcontainer/devcontainer.json` lists a set of extensions, including `"rust-lang.rust"`, to install automatically when the container is created.
1. **Terminal:** Press <kbd>ctrl</kbd>+<kbd>shift</kbd>+<kbd>\`</kbd> and type `uname` and other Linux commands from the terminal window.
1. **Build, Run, and Debug:**
   - Open `main.rs`
   - Add a breakpoint (e.g. on line 8).
   - Press <kbd>F5</kbd> to launch the app in the container.
   - Once the breakpoint is hit, try hovering over variables, examining locals, and more.
 
## Contributing

This project welcomes contributions and suggestions. Most contributions require you to agree to a
Contributor License Agreement (CLA) declaring that you have the right to, and actually do, grant us
the rights to use your contribution. For details, visit https://cla.microsoft.com.

When you submit a pull request, a CLA-bot will automatically determine whether you need to provide
a CLA and decorate the PR appropriately (e.g., label, comment). Simply follow the instructions
provided by the bot. You will only need to do this once across all repos using our CLA.

This project has adopted the [Microsoft Open Source Code of Conduct](https://opensource.microsoft.com/codeofconduct/).
For more information see the [Code of Conduct FAQ](https://opensource.microsoft.com/codeofconduct/faq/) or
contact [opencode@microsoft.com](mailto:opencode@microsoft.com) with any additional questions or comments.

## License

Copyright © Microsoft Corporation All rights reserved.<br />
Licensed under the MIT License. See LICENSE in the project root for license information.
