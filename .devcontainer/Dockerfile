# See here for image contents: https://github.com/microsoft/vscode-dev-containers/tree/v0.195.0/containers/rust/.devcontainer/base.Dockerfile
# [Choice] Debian OS version (use bullseye on local arm64/Apple Silicon): buster, bullseye
ARG VARIANT="bullseye"
FROM mcr.microsoft.com/vscode/devcontainers/rust:1-${VARIANT}

# [Optional] Uncomment this section to install additional packages.
# RUN apt-get update && export DEBIAN_FRONTEND=noninteractive \
#     && apt-get -y install --no-install-recommends <your-package-list-here>

RUN apt install -y curl

# Install Solana
RUN sh -c "$(curl -sSfL https://release.solana.com/v1.7.12/install)"
RUN mv /root/.local/share/solana /usr/local/bin
ENV PATH      $PATH:/usr/local/bin/solana/install/releases/1.7.12/solana-release/bin

# Install NVM and install node.js
ENV NVM_DIR /usr/local/nvm
ENV NODE_VERSION 16.9.1

WORKDIR $NVM_DIR

RUN curl https://raw.githubusercontent.com/creationix/nvm/master/install.sh | bash \
    && . $NVM_DIR/nvm.sh \
    && nvm install $NODE_VERSION \
    && nvm alias default $NODE_VERSION \
    && nvm use default

ENV NODE_PATH $NVM_DIR/versions/node/v$NODE_VERSION/lib/node_modules
ENV PATH      $NVM_DIR/versions/node/v$NODE_VERSION/bin:$PATH