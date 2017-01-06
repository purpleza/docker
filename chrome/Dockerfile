FROM purpleza/x11-client

MAINTAINER PurpleZa <purpleza@gmail.com>

# install chrome
RUN apk --no-cache --update --upgrade add \
    udev \
#    mesa-gl \
    chromium

RUN apk --no-cache add curl \
    && curl -O https://fpdownload.adobe.com/pub/flashplayer/pdc/24.0.0.186/flash_player_ppapi_linux.x86_64.tar.gz \
    && mkdir flash && tar xf *.gz -C flash \
    && mkdir /usr/lib/PepperFlash \
    && cp flash/*.* /usr/lib/PepperFlash \
    && rm -rf ~/* \
    && apk del --purge curl
    
COPY chrome.conf /etc/supervisor.d/chrome.conf

VOLUME /data
