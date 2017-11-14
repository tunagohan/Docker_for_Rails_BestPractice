FROM nginx:1.13.2

RUN apt-get update && \
    apt-get install -y apt-utils \
                       locales && \
    echo "ja_JP.UTF-8 UTF-8" > /etc/locale.gen && \
    locale-gen ja_JP.UTF-8
ENV LC_ALL ja_JP.UTF-8

RUN rm -f /etc/nginx/conf.d/*
ADD ./nginx/nginx.conf /etc/nginx/conf.d/app.conf

CMD /usr/sbin/nginx -g 'daemon off;' -c /etc/nginx/nginx.conf
