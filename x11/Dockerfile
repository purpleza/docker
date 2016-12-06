FROM alpine:latest

# Setup environment variables
ENV HOME=/root \
    DEBIAN_FRONTEND=noninteractive \
	LANG=en_HK.UTF-8 \
	LANGUAGE=en_HK.UTF-8 \
	LC_ALL=en_HK.UTF-8 \
	TZ=Asia/Hong_Kong \
	DISPLAY=:0.0 \
	DISPLAY_SCREEN=1280x1024x15

# x11vnc is in testing repo
RUN echo "http://dl-6.alpinelinux.org/alpine/edge/testing" >> /etc/apk/repositories

# Install git, supervisor, VNC, & X11 packages
RUN apk --update --upgrade add \
    bash \
    xvfb \
	x11vnc \
	socat \
	jwm \
	git \
	supervisor

# Clone noVNC from github
RUN git clone https://github.com/kanaka/noVNC.git /root/noVNC \
	&& git clone https://github.com/kanaka/websockify /root/noVNC/utils/websockify \
	&& rm -rf /root/noVNC/.git \
	&& rm -rf /root/noVNC/utils/websockify/.git \
	&& apk del git

COPY supervisord.conf /etc/supervisor/conf.d/supervisord.conf

# Modify the launch script 'ps -p'
RUN sed -i -- "s/ps -p/ps -o pid | grep/g" /root/noVNC/utils/launch.sh

EXPOSE 8080

CMD ["/usr/bin/supervisord", "-c", "/etc/supervisor/conf.d/supervisord.conf"]