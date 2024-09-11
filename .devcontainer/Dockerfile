FROM mcr.microsoft.com/devcontainers/base:jammy

USER vscode
WORKDIR /home/vscode

RUN curl -O http://ftp.gnu.org/gnu/wget/wget-1.21.3.tar.gz
RUN tar -xzf wget-1.21.3.tar.gz
RUN cd wget-1.21.3
RUN ./configure
RUN make
RUN make install

RUN apt-get update && apt-get install sudo git curl git bash-completion python3 python3-pip -y && apt-get clean

RUN sudo apt update
RUN sudo apt install wget
RUN sudo wget --version

RUN wget -q https://raw.githubusercontent.com/leanprover-community/mathlib-tools/master/scripts/install_debian.sh && bash install_debian.sh ; rm -f install_debian.sh && source ~/.profile


ENV PATH="/home/vscode/.elan/bin:${PATH}"

RUN echo finished
