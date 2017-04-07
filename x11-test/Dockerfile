FROM purpleza/ubuntu

# Setup environment variables
ENV DISPLAY=:0 \
	DISPLAY_SCREEN=1280x1024

# Install X11 packages
RUN apt-get update && \
    apt-get install -y --no-install-recommends \
    x11-xserver-utils \
    xfonts-base \
	dbus-x11 \
    fonts-noto-cjk \
	tightvncserver \
	jwm \
	fcitx-table-cangjie5 \
	fcitx-frontend-gtk3 \
	fcitx-ui-classic \
	xterm \
	&& apt-get clean

COPY vnc/* .vnc/

RUN chmod u+x .vnc/xstartup

COPY *.conf /etc/supervisor/conf.d/

EXPOSE 5900 6000
