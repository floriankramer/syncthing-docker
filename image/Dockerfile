FROM ubuntu:22.04

RUN apt-get update && DEBIAN_FRONTEND=noninteractive apt-get install -y --no-install-recommends \
  ca-certificates \
  curl

RUN useradd -s /bin/bash -m -U -u 9999 syncthing
USER syncthing


RUN curl -L https://github.com/syncthing/syncthing/releases/download/v1.20.3/syncthing-linux-amd64-v1.20.3.tar.gz \
  -o /home/syncthing/syncthing.tar.gz && \
  cd /home/syncthing && \
  gunzip ./syncthing.tar.gz && \
  tar -xvf ./syncthing.tar && \
  rm syncthing.tar && \
  mv syncthing* syncthing

CMD [ "/home/syncthing/syncthing/syncthing", "--gui-address=0.0.0.0:8384" ]
