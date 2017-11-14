FROM ruby:2.4.2

RUN apt-get update -qq && \
    apt-get install -y apt-utils \
                       build-essential \
                       libpq-dev \
                       nodejs \
                       mysql-client

RUN mkdir /app
WORKDIR /app
ADD ./kintai_contact_web/Gemfile /app/Gemfile
ADD ./kintai_contact_web/Gemfile.lock /app/Gemfile.lock
RUN bundle install -j4
ADD ./kintai_contact_web /app
RUN mkdir -p tmp/sockets

EXPOSE 3000
