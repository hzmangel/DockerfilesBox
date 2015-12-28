FROM debian:latest
MAINTAINER Hu Ziming <hzmangel@gmail.com>

# Replace to CHN mirror, since the default httpredir is not working on this fancied land
RUN sed -i.orig 's/httpredir.debian.org/mirrors.163.com/g' /etc/apt/sources.list
RUN apt-get update && apt-get install -y nodejs npm ruby ruby-dev --no-install-recommends && rm -rf /var/lib/apt/lists/*

