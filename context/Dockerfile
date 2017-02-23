FROM base/archlinux

# enable multilib
RUN /bin/echo -e '[multilib]\nInclude = /etc/pacman.d/mirrorlist\n' >> /etc/pacman.conf

# install & upgrade base stuff
RUN pacman -Sy --noconfirm archlinux-keyring
RUN pacman -S --noconfirm pacman
RUN pacman-db-upgrade
RUN pacman -Su --noconfirm

# graphics driver
RUN pacman -S --noconfirm xf86-video-amdgpu
# steam
RUN pacman -S --noconfirm steam steam-native-runtime

# additional stuff
RUN pacman -S --noconfirm sudo

RUN useradd -m -u 1000 -s /bin/bash runner

USER runner
WORKDIR /home/runner
