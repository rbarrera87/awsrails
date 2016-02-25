FROM ubuntu:14.04

#Ruby
RUN apt-key adv --keyserver keyserver.ubuntu.com --recv-keys C3173AA6 \
    && echo "deb http://ppa.launchpad.net/brightbox/ruby-ng/ubuntu trusty main" >> /etc/apt/sources.list.d/ruby.list \
    && apt-get update \
    && apt-get install -y ruby2.2 ruby2.2-dev bundler \
    && apt-get clean && rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/*

#Dependencies
RUN apt-get update \
    && apt-get install -y build-essential nodejs libmysqlclient-dev libsqlite3-dev libpq-dev git \
    && apt-get clean && rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/*

#bundler
RUN gem install bundler

ENV APP_HOME /webapps/awsrails
RUN mkdir -p $APP_HOME
WORKDIR $APP_HOME

#Gemfiles
COPY Gemfile Gemfile.lock ./


#gems
RUN bundle install

#commands
EXPOSE 3000
CMD ["rails", "server", "-b", "0.0.0.0"]

COPY . ./
