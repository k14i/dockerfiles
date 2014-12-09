FROM keithseahus/base-ubuntu-14.04lts
MAINTAINER Keisuke Takahashi <keithseahus@gmail.com>

ENV REFRESHED_AT 2014-12-09

USER root

RUN apt-get update
RUN apt-get upgrade -y

RUN locale-gen en_US.UTF-8
ENV LANG en_US.UTF-8
ENV LANGUAGE en_US:en
ENV LC_ALL en_US.UTF-8

RUN rm -f /bin/sh && ln -s /bin/zsh /bin/sh

USER dev

RUN curl -sSL https://rvm.io/mpapis.asc | gpg --import - \
    && \curl -sSL https://get.rvm.io | bash -s stable \
    && source ~/.profile \
    && source ~/.rvm/scripts/rvm \
    && echo "source ~/.rvm/scripts/rvm" >> ~/.bashrc \
    && ~/.rvm/bin/rvm get stable

