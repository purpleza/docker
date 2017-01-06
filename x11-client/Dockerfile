FROM purpleza/alpine

# install chinese fonts
RUN apk --no-cache --update --upgrade add curl \
    && curl -O http://mirrors.cicku.me/archlinux/community/os/i686/adobe-source-han-sans-tw-fonts-1.004-1-any.pkg.tar.xz \
    && curl -O http://mirrors.cicku.me/archlinux/community/os/i686/adobe-source-han-sans-cn-fonts-1.004-1-any.pkg.tar.xz \
    && mkdir fonts && tar xf *.xz -C fonts \
    && cp -R fonts/usr/share/fonts /usr/share/fonts \
    && cp -R fonts/etc/fonts /etc/fonts \
    && rm -rf ~/* \
    && apk del --purge curl