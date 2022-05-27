FROM ubuntu:18.04

RUN apt update && apt upgrade -y
RUN apt install -y bind9 bind9utils bind9-doc dnsutils -y
EXPOSE 53/UDP
EXPOSE 53/TCP

COPY named.conf /etc/bind/

CMD ["named", "-g"]
