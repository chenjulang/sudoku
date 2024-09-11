ARG VARIANT="jammy"
FROM mcr.microsoft.com/vscode/devcontainers/base:0-${VARIANT}

RUN apt-get update && apt-get install sudo git curl git bash-completion python3 python3-pip -y && apt-get clean

# 安装wget
RUN sudo apt update
RUN sudo apt install wget
RUN sudo wget --version

USER vscode
RUN echo $HOME
RUN wget -q https://raw.githubusercontent.com/leanprover-community/mathlib-tools/master/scripts/install_debian.sh && bash install_debian.sh ; rm -f install_debian.sh && source ~/.profile
