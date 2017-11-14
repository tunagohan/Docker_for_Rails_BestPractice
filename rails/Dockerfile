FROM ruby:2.4.2

RUN apt-get update -qq && \
    apt-get install -y apt-utils \
                       build-essential \
                       libpq-dev \
                       nodejs \
                       mysql-client

ENV APPPATH {app_path}
RUN mkdir /app
WORKDIR /app
ADD ./$APPPATH/Gemfile /app/Gemfile
ADD ./$APPPATH/Gemfile.lock /app/Gemfile.lock
RUN bundle install -j4
ADD ./$APPPATH /app
RUN mkdir -p tmp/sockets

EXPOSE 3000
