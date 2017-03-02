FROM purpleza/x11-client

MAINTAINER PurpleZa <purpleza@gmail.com>

USER $USER

COPY files /

ADD https://dl.google.com/linux/linux_signing_key.pub /tmp/

# Setup
RUN apt-key add /tmp/linux_signing_key.pub \
    && echo "deb [arch=amd64] http://dl.google.com/linux/chrome/deb/ stable main" >> /etc/apt/sources.list.d/google.list \
    && echo "deb [arch=amd64] http://archive.canonical.com/ubuntu/ xenial partner" > /etc/apt/sources.list.d/canonical.list \
    && mkdir -p /usr/share/icons/hicolor # fix xdg-icon-resource no writable system icon directory found

# Install
RUN apt-get update \
    && apt-get install -y --no-install-recommends \
        google-chrome-stable \
        adobe-flashplugin \
    && apt-get clean \
    && rm -rf /var/cache/* /var/log/apt/* /tmp/*

VOLUME ["/data"]