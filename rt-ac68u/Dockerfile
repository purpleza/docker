FROM debian:latest
MAINTAINER PurpleZa <purpleza@gmail.com>
WORKDIR /root

# Setup environment variables
ENV HOME=/root \
    DEBIAN_FRONTEND=noninteractive \
	LANG=en_HK.UTF-8 \
	LANGUAGE=en_HK.UTF-8 \
	LC_ALL=en_HK.UTF-8 \
	TZ=Asia/Hong_Kong \
	CC=OUTPUTFROMGREP \
	PATH=$PATH:/opt/brcm/hndtools-mipsel-uclibc/bin

RUN dpkg --add-architecture i386 && \
    apt-get update && \
    apt-get --no-install-recommends install -y autoconf automake bash bison bzip2 diffutils file flex g++ gawk gcc-multilib gettext gperf groff-base libncurses-dev libexpat1-dev libslang2 libssl-dev libtool libxml-parser-perl make patch perl pkg-config python sed shtool tar texinfo unzip zlib1g zlib1g-dev lib32z1-dev lib32stdc++6 libelf-dev:i386 libelf1:i386 git curl

RUN cd /root && \
    git clone https://github.com/RMerl/asuswrt-merlin.git

RUN ln -s ~/asuswrt-merlin/tools/brcm /opt/brcm && \
    ln -s ~/asuswrt-merlin/release/src-rt-6.x.4708/toolchains/hndtools-arm-linux-2.6.36-uclibc-4.5.3 /opt/brcm-arm && \
    cd ~/asuswrt-merlin/release/src-rt-6.x.4708 && \
    make clean 2>&1 | grep -oE '(mipsel|arm).*gcc' | uniq

CMD ["bash"]