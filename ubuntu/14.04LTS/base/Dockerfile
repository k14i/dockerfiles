FROM ubuntu:14.04
MAINTAINER Keisuke Takahashi <keithseahus@gmail.com>

ENV REFRESHED_AT 2014-12-07

RUN apt-get update
RUN apt-get upgrade -y

RUN locale-gen en_US.UTF-8
ENV LANG en_US.UTF-8
ENV LANGUAGE en_US:en
ENV LC_ALL en_US.UTF-8

RUN apt-get install -y \
    python \
    openssl \
    libssl-dev \
    automake \
    build-essential \
    curl \
    wget \
    git \
    vim \
    emacs \
    zsh \
    screen \
    tmux

RUN useradd -s /bin/zsh -m dev
RUN echo 'dev ALL=(ALL:ALL) NOPASSWD:ALL' | tee /etc/sudoers.d/dev
WORKDIR /home/dev
ENV HOME /home/dev
USER dev
RUN git clone https://github.com/keithseahus/dotfiles.git ~/.dotfiles \
    && cd ~/.dotfiles \
    && python ./set_symlinks_to_dotfiles.py
CMD ["zsh"]
