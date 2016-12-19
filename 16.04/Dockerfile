FROM ubuntu:16.04
MAINTAINER Kevin McBride <krmcbride.io@gmail.com>

RUN echo "America/Los_Angeles" > /etc/timezone
RUN /usr/sbin/dpkg-reconfigure -f noninteractive tzdata

# Install vim, git, curl, etc
RUN apt-get update \
  && apt-get remove -y \
    vim-common \
    vim-runtime \
  && apt-get install -y --no-install-recommends \
    ca-certificates \
    curl \
    wget \
    openssh-client \
    git \
    vim \
    ctags \
  && rm -rf /var/lib/apt/lists/*

# Bash enhancements
RUN git clone --depth=1 https://github.com/Bash-it/bash-it.git /root/.bash_it
RUN /root/.bash_it/install.sh --silent
COPY bashrc /root/.bashrc
COPY custom.aliases.bash /root/.bash_it/custom/
COPY docker.theme.bash /root/.bash_it/themes/docker/

# Vim enhancements
RUN git clone --depth=1 git://github.com/amix/vimrc.git /root/.vim_runtime
RUN sh /root/.vim_runtime/install_awesome_vimrc.sh

# Create a commonly used onbuild directory
RUN mkdir /usr/src/app

# Move to a better default working directory
WORKDIR /root

CMD ["/bin/bash"]
