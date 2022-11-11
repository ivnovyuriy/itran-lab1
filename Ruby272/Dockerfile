FROM ubuntu:20.04

LABEL maintainer "Ivanov Yuriy <ivanovyuriy@gmail.com>"

RUN apt-get update && \
    apt-get install -y \
        git \
        curl \
        wget \
        gcc \
        make \
        libssl-dev \
        zlib1g-dev \
        libmysqlclient-dev \
        redis-server \
        libsqlite3-dev

# Install ruby-install
RUN cd /tmp &&\
  wget -O ruby-install-0.6.1.tar.gz https://github.com/postmodern/ruby-install/archive/v0.6.1.tar.gz &&\
  tar -xzvf ruby-install-0.6.1.tar.gz &&\
  cd ruby-install-0.6.1/ &&\
  make install

# Install MRI Ruby
RUN ruby-install ruby 2.7.2

# Add Ruby binaries to $PATH
ENV PATH /opt/rubies/ruby-2.7.2/bin:$PATH 

CMD [ "irb" ]