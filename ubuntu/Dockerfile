FROM ubuntu:latest

# Setup environment variables
ENV HOME=/root \
	LANG=en_HK.UTF-8 \
	LANGUAGE=en_HK.UTF-8 \
	LC_ALL=en_HK.UTF-8 \
	TZ=Asia/Hong_Kong

WORKDIR $HOME

RUN apt-get update && apt-get upgrade -y \
    && apt-get install -y supervisor \
    && apt-get clean

COPY supervisord.conf /etc/supervisor/supervisord.conf

CMD ["/usr/bin/supervisord", "-c", "/etc/supervisor/supervisord.conf"]