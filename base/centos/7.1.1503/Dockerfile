FROM centos:7.1.1503
MAINTAINER Keisuke Takahashi <keithseahus@gmail.com>

ENV REFRESHED_AT 2015-06-06

RUN yum update -y

ENV LANG en_US.UTF-8
ENV LANGUAGE en_US:en
ENV LC_ALL en_US.UTF-8

RUN yum install -y \
    python \
    openssl \
    openssl-devel \
    automake \
    curl \
    wget \
    git \
    vim-enhanced \
    emacs \
    zsh \
    screen \
    tmux \
    the_silver_searcher \
    tcpdump \
    nmap \
    htop \
    mosh \
    sudo

RUN useradd -s /bin/zsh -m dev
RUN echo 'dev ALL=(ALL:ALL) NOPASSWD:ALL' | tee /etc/sudoers.d/dev
WORKDIR /home/dev
ENV HOME /home/dev
USER dev
RUN git clone https://github.com/keithseahus/dotfiles.git ~/.dotfiles \
    && cd ~/.dotfiles \
    && python ./set_symlinks_to_dotfiles.py

