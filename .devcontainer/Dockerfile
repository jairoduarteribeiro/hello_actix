FROM rust:1.81.0

ARG USERNAME=dev
ARG USER_UID=1000
ARG USER_GID=$USER_UID

RUN export DEBIAN_FRONTEND=noninteractive && \
    apt-get update && \
    apt-get install -y --no-install-recommends \
        git \
        vim \
        gnupg \
        openssh-client \
        bash-completion && \
    apt-get clean && \
    rm -rf /var/lib/apt/lists/* && \
    groupadd --gid $USER_GID $USERNAME && \
    useradd --uid $USER_UID --gid $USER_GID -m -s /bin/bash $USERNAME

USER $USERNAME
