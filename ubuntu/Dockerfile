FROM ubuntu:latest

# Setup environment variables
ENV LANG=en_HK.UTF-8 \
	LANGUAGE=en_HK.UTF-8 \
	LC_ALL=en_HK.UTF-8 \
	TZ=Asia/Hong_Kong \
	USER=user \
	HOME=/home/$USER

RUN locale-gen en_HK.UTF-8 && update-locale

RUN apt-get update && apt-get upgrade -y \
    && apt-get install --no-install-recommends -y \
        whiptail \
        psmisc \
        wget \
        apt-utils \
        vim \
        supervisor \
    && apt-get autoremove -y \
    && apt-get clean \
    && rm -rf /var/cache/* /var/log/apt/* /tmp/*

COPY files /

RUN useradd -m $USER

CMD ["/usr/bin/supervisord", "-c", "/etc/supervisor/supervisord.conf"]