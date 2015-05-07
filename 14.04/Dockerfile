FROM ubuntu:14.04
MAINTAINER Kevin McBride <krmcbride.io@gmail.com>

# Bash enhancements
COPY bash_aliases.sh /etc/skel/.bash_aliases
COPY bash_aliases.sh /root/.bash_aliases
COPY bash_prompt.sh /etc/skel/.bash_prompt
COPY bash_prompt.sh /root/.bash_prompt

# Vim enhancements
COPY vimrc /etc/skel/.vimrc
COPY vimrc /root/.vimrc

# Git
RUN apt-get update && apt-get install -y git && rm -rf /var/lib/apt/lists/*
COPY gitconfig /etc/gitconfig

# Create a non-root user
RUN useradd -rm -s /bin/bash app

# Create a directory that apps can use
RUN mkdir /usr/src/app

# Move to a better default working directory
WORKDIR /root

# Install some small utilities
RUN apt-get update && apt-get install -y \
  curl \
  wget \
  && rm -rf /var/lib/apt/lists/*

# Configure the app directory as a volume
VOLUME /usr/src/app
