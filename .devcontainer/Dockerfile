FROM mcr.microsoft.com/devcontainers/cpp:ubuntu-22.04

RUN sudo apt-get update && \
    sudo apt-get install -y git \
                            curl \
                            zip \
                            unzip \
                            vim

# install other


ARG USERNAME=vscode
ARG USER_UID=1000
ARG USER_GID=$USER_UID

RUN groupmod --gid $USER_GID $USERNAME \
  && usermod --uid $USER_UID --gid $USER_GID $USERNAME \
  && chown -R $USER_UID:$USER_GID /home/$USERNAME

# ********************************************************
# * Anything else you want to do like clean up goes here *
# ********************************************************

# [Optional] Set the default user. Omit if you want to keep the default as root.
USER $USERNAME

# install vim
RUN git clone --depth=1 https://github.com/amix/vimrc.git ${HOME}/.vim_runtime && \
              sh ${HOME}/.vim_runtime/install_awesome_vimrc.sh

