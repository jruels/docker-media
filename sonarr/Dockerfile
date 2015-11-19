# vim:set ft=dockerfile:

FROM debian:jessie

MAINTAINER Jason Smith <jason@smithss.org>

## Add couchpotato repo
RUN apt-key adv --keyserver keyserver.ubuntu.com --recv-keys FDA5DFFC && \
echo "deb http://apt.sonarr.tv/ master main" | sudo tee /etc/apt/sources.list.d/sonarr.list && \
apt-get -q update && \
apt-get install -yq nzbdrone && \
apt-get clean && \
rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/*

VOLUME /config /downloads /tv
EXPOSE 8989

CMD mono --debug /opt/NzbDrone/NzbDrone.exe 
