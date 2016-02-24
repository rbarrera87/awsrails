FROM ubuntu

#Update things
RUN apt-get update
RUN apt-get install -y gcc-4.6-base
RUN apt-get install -y cpp-4.6
RUN apt-get install -y libgomp1
RUN apt-get install -y libquadmath0
RUN apt-get install -y libc6-dev

RUN apt-get install -y build-essential

#sudo apt-get install git-core curl zlib1g-dev build-essential libssl-dev libreadline-dev libyaml-dev libsqlite3-dev sqlite3 libxml2-dev libxslt1-dev libcurl4-openssl-dev python-software-properties libffi-dev


#dependencies
RUN apt-get install -y git-core
RUN apt-get install -y curl
RUN apt-get install -y libc6
RUN apt-get install -y libc6-dev
RUN apt-get install -y libc-dev
RUN apt-get install -y zlib1g-dev
RUN apt-get install -y build-essential
RUN apt-get install -y libssl-dev
RUN apt-get install -y libreadline-dev
RUN apt-get install -y libyaml-dev
RUN apt-get install -y libxml2-dev
RUN apt-get install -y libxslt1-dev
RUN apt-get install -y libcurl4-openssl-dev
RUN apt-get install -y software-properties-common
RUN apt-get install -y libffi-dev
RUN apt-get install -y wget
RUN wget http://ftp.ruby-lang.org/pub/ruby/2.3/ruby-2.3.0.tar.gz
RUN tar -xzvf ruby-2.3.0.tar.gz &&  cd ruby-2.3.0/ && ./configure && make && make install


#Install things
#bundler
RUN gem install bundler


#Cloning repo using http
RUN git clone https://github.com/rbarrera87/awsrails.git

#gems
RUN cd awsrails/ && bundle install

#database
#RUN bundle exec rake db:create
#RUN bundle exec rake db:migrate
