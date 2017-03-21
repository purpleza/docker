FROM purpleza/ubuntu

ENV GTK_IM_MODULE=fcitx
ENV QT_IM_MODULE=fcitx
ENV XMODIFIERS=@im=fcitx 

COPY files /

# install chinese fonts
RUN apt-get update && apt-get install -y --no-install-recommends \
    fonts-noto-cjk \
    fcitx-table-cangjie5 \
    fcitx-frontend-* \
    fcitx-ui-classic \
    fcitx-config-gtk \
    dbus-x11 \
    xterm \
    libgl1-mesa-glx \
    iso-codes \
    x11-utils \
    && apt-get clean \
    && rm -rf /var/cache/* /var/log/apt/* /tmp/*

VOLUME ["/tmp/.X11.unix/"]
