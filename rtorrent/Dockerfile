FROM debian:testing

EXPOSE 5000

RUN apt update && apt install -y rtorrent \
&& mkdir /var/log/rtorrent

ENTRYPOINT /usr/bin/rtorrent &