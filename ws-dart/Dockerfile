FROM cloud9/workspace
MAINTAINER Kendal Harland <kendaljharland@gmail.com>

# Steps taken from https://www.dartlang.org/install/linux

ADD ./files/workspace /home/ubuntu/workspace

# Enable HTTPS for apt.
RUN sudo apt-get update
RUN sudo apt-get install apt-transport-https

# Get the Google Linux package signing key.
RUN sudo sh -c 'curl https://dl-ssl.google.com/linux/linux_signing_key.pub |\
    apt-key add -'

# Set up the location of the stable repository.
RUN sudo sh -c 'curl https://storage.googleapis.com/download.dartlang.org/linux/debian/dart_stable.list > /etc/apt/sources.list.d/dart_stable.list'

RUN sudo apt-get update
RUN sudo apt-get install dart/stable

RUN chmod -R g+w /home/ubuntu/workspace && \
    chown -R ubuntu:ubuntu /home/ubuntu

ADD ./files/check-environment /.check-environment/dart
