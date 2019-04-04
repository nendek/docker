FROM ruby:latest

RUN apt-get update && \
	apt-get install build-essential libpq-dev\
	sqlite3 nodejs -y && \
	gem install rails

RUN mkdir /opt/app

ONBUILD WORKDIR /opt/app

ONBUILD ADD app/ /opt/app

ONBUILD RUN bundle install && \
		rake db:migrate && \
		rake db:setup && \
		rake db:seed

#docker build -t ft-rails:on-build .
#docker run -it --rm ft-rails:on-build
