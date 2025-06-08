FROM ubuntu:latest

# install sudo 
RUN apt-get update && \
    apt-get install -y sudo neovim curl && \
    apt-get clean

# create user w/ sudo 
RUN useradd -m -s /bin/bash sysadmin && \
    echo 'sysadmin ALL=(ALL) NOPASSWD:ALL' >> /etc/sudoers

# switch to new user 
USER sysadmin
WORKDIR /home/sysadmin

# env var
ENV HOME=/home/sysadmin
