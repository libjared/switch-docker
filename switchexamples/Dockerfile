FROM switchdev:latest
MAINTAINER libjared

ENV DEVKITPRO /opt/devkitpro
ENV DEVKITARM /opt/devkitpro/devkitARM
ENV DEVKITPPC /opt/devkitpro/devkitPPC

RUN : \
  && cd /opt/devkitpro/examples/switch \
  && make

# todo copy out
CMD ["/bin/bash"]
