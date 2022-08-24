FROM ubuntu:18.04

RUN apt-get -y update && apt-get -y upgrade
RUN apt-get install vim nano dnsutils net-tools asterisk -y



COPY sip.conf /etc/asterisk/sip.conf
COPY extensions.conf /etc/asterisk/extensions.conf
COPY voicemail.conf /etc/asterisk/voicemail.conf
COPY users.conf /etc/asterisk/users.conf
COPY rtp.conf /etc/asterisk/rtp.conf


EXPOSE 5060/UDP
EXPOSE 10000-10020/UDP

ENTRYPOINT [ "/usr/sbin/asterisk", "-f" ]
