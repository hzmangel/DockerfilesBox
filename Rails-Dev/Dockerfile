FROM ruby:2.2
MAINTAINER Hu Ziming <hzmangel@gmail.com>

# Replace to CHN mirror, since the default httpredir is not working on this fancied land
RUN sed -i.orig 's/httpredir.debian.org/mirrors.163.com/g' /etc/apt/sources.list
RUN sed -i.orig 's#security.debian.org#mirrors.163.com/debian-security#g' /etc/apt/sources.list
RUN apt-get update
RUN apt-get install -y \
        nodejs npm \
        build-essential \
        libmysqlclient-dev mysql-client postgresql-client sqlite3 \
        --no-install-recommends
RUN ln -s /usr/bin/nodejs /usr/bin/node
RUN rm -rf /var/lib/apt/lists/*


# Change to use Taobao mirror
RUN gem sources --add https://ruby.taobao.org/ --remove https://rubygems.org/
RUN echo 'gem: --no-document' >> ~/.gemrc

# Rails related
RUN gem install rails bundler

# Install bower for rails-bower gem, and enable root to run bower command
RUN npm install -g bower --registry=https://registry.npm.taobao.org
RUN echo '{ "allow_root": true }' > ~/.bowerrc

