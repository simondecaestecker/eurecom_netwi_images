FROM gns3/webterm
MAINTAINER Simon DECAESTECKER <contact@simondecaestecker.com>

RUN apt-get update -y && \
    apt-get install -y debconf-utils

RUN echo iptables-persistent iptables-persistent/autosave_v4 boolean true | debconf-set-selections && \
    echo iptables-persistent iptables-persistent/autosave_v6 boolean true | debconf-set-selections

RUN apt-get install -y iptables iptables-persistent python python3 mailutils alpine dovecot-pop3d dovecot-imapd

ADD entrypoint.sh /entrypoint.sh
RUN chmod +x entrypoint.sh
CMD [ "/entrypoint.sh" ]
