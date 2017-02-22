FROM purpleza/ubuntu

# Install packages
RUN apt-get update && \
    apt-get install -y --no-install-recommends \
    openssh-client \
    ssh-askpass-gnome \
    libgl1-mesa-glx \
    virt-manager \
    && apt-get clean

ENTRYPOINT ["setsid", "virt-manager"]