FROM ruby:latest

RUN apt-get update && \
	apt-get install nodejs -y && \
	gem install rails

RUN mkdir /opt/app

ONBUILD WORKDIR /opt/app

ONBUILD ADD app/ /opt/app

ONBUILD RUN bundle install

ONBUILD RUN bundle install && \
		rake db:migrate && \
		rake db:setup && \
		rake db:seed
