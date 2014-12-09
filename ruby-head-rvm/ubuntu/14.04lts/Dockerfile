FROM keithseahus/rvm-ubuntu-14.04lts
MAINTAINER Keisuke Takahashi <keithseahus@gmail.com>

ENV REFRESHED_AT 2014-12-09

USER root

RUN apt-get update
RUN apt-get upgrade -y

ENV RUBY_VERSION ruby-head

RUN locale-gen en_US.UTF-8
ENV LANG en_US.UTF-8
ENV LANGUAGE en_US:en
ENV LC_ALL en_US.UTF-8

USER dev

RUN ~/.rvm/bin/rvm install ${RUBY_VERSION}

RUN /bin/bash -l -c rvm requirements
ENV PATH ~/.rvm/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
RUN /bin/bash -l -c "rvm use ${RUBY_VERSION} --default"

RUN /bin/bash -l -c 'gem install bundler --no-doc --no-ri'

