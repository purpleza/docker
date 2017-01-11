FROM purpleza/alpine

MAINTAINER PurpleZa <purpleza@gmail.com>

# install node.js
RUN apk --no-cache --update --upgrade add \
    git \
    nodejs

# depoly proxy system

RUN git clone https://deploy:Deploy_GitDg@git.purpleza.com/za/proxy.git \
    && cd proxy \
    && npm install

COPY proxy.conf /etc/supervisor.d/

EXPOSE 9001