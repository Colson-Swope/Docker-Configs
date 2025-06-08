FROM ubuntu:latest

# install sudo, neovim, curl
RUN apt-get update && \
    apt-get install -y sudo neovim curl && \
    apt-get clean

    # create user w/ sudo
RUN useradd -m -s /bin/bash sysadmin && \
    echo 'sysadmin ALL=(ALL) NOPASSWD:ALL' >> /etc/sudoers

# add color to prompt
RUN echo "force_color_prompt=yes" >> /home/sysadmin/.bashrc && \
    echo "PS1='\\[\\e[1;32m\\]\\u@\\h:\\w\\$ \\[\\e[0m\\]'" >> /home/sysadmin/.bashrc && \
    chown sysadmin:sysadmin /home/sysadmin/.bashrc

# set env var and switch to user
ENV HOME=/home/sysadmin
USER sysadmin
WORKDIR /home/sysadmin
