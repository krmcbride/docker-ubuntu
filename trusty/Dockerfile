FROM ubuntu:14.04
MAINTAINER Kevin McBride <kmcbride@sourceintelligence.com>

# Bash enhancements
COPY bash_aliases.sh /etc/skel/.bash_aliases
COPY bash_aliases.sh /root/.bash_aliases
COPY bash_prompt.sh /etc/skel/.bash_prompt
COPY bash_prompt.sh /root/.bash_prompt

# Vim enhancements
COPY vimrc /etc/skel/.vimrc
COPY vimrc /root/.vimrc

# Create a non-root user
RUN useradd -rm -s /bin/bash source44

# Move to a better default working directory
WORKDIR /root
