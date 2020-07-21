FROM debian:10

RUN apt update && apt install -y bind9 bind9utils bind9-doc
RUN sed -i 's/OPTIONS=.*/OPTIONS="-4 -u bind"/' /etc/default/bind9

WORKDIR /etc/bind
COPY ./named.conf.options .
COPY ./named.conf.local .
COPY ./db.rpz .

CMD /etc/init.d/bind9 start && /bin/bash -c "while :; do sleep 10; done"
