FROM purpleza/ubuntu

ENV GTK_IM_MODULE=xim
ENV QT_IM_MODULE=xim
ENV XMODIFIERS=@im=fcitx

COPY files /

# install chinese fonts
RUN apt-get update && apt-get install -y --no-install-recommends \
    fonts-noto-cjk \
    fcitx-table-cangjie5 \
    fcitx-frontend-gtk3 \
    fcitx-ui-classic \
    fcitx-config-gtk \
    dbus-x11 \
    && apt-get clean \
    && rm -rf /var/cache/* /var/log/apt/* /tmp/*

VOLUME ["/tmp/.X11.unix/"]
