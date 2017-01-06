FROM purpleza/alpine

# Setup environment variables
ENV DISPLAY=:0 \
	DISPLAY_SCREEN=1280x1024x15

# Install X11 packages
RUN apk --no-cache --update --upgrade add \
    bash \
    xvfb \
	socat \
	jwm

# Build x11vnc dependencies
RUN apk --no-cache --update add \
    git autoconf automake g++ make \
    openssl-dev libvncserver-dev

# Build & install x11vnc
RUN git clone https://github.com/LibVNC/x11vnc.git /root/x11vnc \
    && cd /root/x11vnc \
    && ./autogen.sh \
        --prefix=/usr \
        --sysconfdir=/etc \
        --mandir=/usr/share/man \
        --infodir=/usr/share/info \
        --localstatedir=/var \
    && make && make install

COPY x11.conf /etc/supervisor.d/x11.conf

EXPOSE 5900