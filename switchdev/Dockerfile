FROM archimg/base:full
MAINTAINER libjared

COPY pacman.conf.append /tmp/

RUN : \
# basic devkitpro environment
  && pacman-key --recv F7FD5492264BB9D0 \
  && pacman-key --lsign F7FD5492264BB9D0 \
  && cat /tmp/pacman.conf.append >> /etc/pacman.conf \
  && pacman --noconfirm -U https://downloads.devkitpro.org/devkitpro-keyring-r1.787e015-2-any.pkg.tar.xz \
  && pacman --noconfirm --needed -Syu \
    base-devel \
    switch-dev \
    `pacman -Slq dkp-libs | grep '^switch-'` \
# install some extra switch libs
    switch-freetype \
    switch-glad \
    switch-glm \
    switch-mesa \
# cleanup
  && pacman --noconfirm -Scc

CMD ["/bin/bash"]
