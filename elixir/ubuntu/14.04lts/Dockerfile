FROM keithseahus/erlang-otp-ubuntu-14.04lts
MAINTAINER Keisuke Takahashi <keithseahus@gmail.com>

ENV REFRESHED_AT 2015-06-06

USER root

RUN apt-get update \
    && apt-get upgrade -y \
    && apt-get install nodejs nodejs-dev npm

ENV ELIXIR_VERSION 1.0.4

RUN locale-gen en_US.UTF-8
ENV LANG en_US.UTF-8
ENV LANGUAGE en_US:en
ENV LC_ALL en_US.UTF-8

ENV PATH /bin:/sbin:/usr/bin:/usr/sbin:/usr/local/bin:/usr/local/sbin:/usr/local/erlang/bin:/usr/local/elixir/bin

ADD https://github.com/elixir-lang/elixir/archive/v${ELIXIR_VERSION}.tar.gz /usr/local/src/elixir-${ELIXIR_VERSION}.tar.gz
RUN cd /usr/local/src \
    && tar xzf elixir-${ELIXIR_VERSION}.tar.gz \
    && cd elixir-${ELIXIR_VERSION} \
    && make clean test \
    && ln -snf /usr/local/src/elixir-${ELIXIR_VERSION} /usr/local/elixir \
    && echo -n '/usr/local/elixir/lib' | tee /etc/ld.so.conf.d/elixir

USER dev
ENV PATH /bin:/sbin:/usr/bin:/usr/sbin:/usr/local/bin:/usr/local/sbin:/usr/local/erlang/bin:/usr/local/elixir/bin

