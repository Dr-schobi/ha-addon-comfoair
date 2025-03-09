ARG BUILD_FROM
FROM $BUILD_FROM




RUN apt update
RUN apt upgrade -y
RUN apt install -y git socat python3-paho-mqtt==1.6.1 python3-serial python3-yaml

WORKDIR /bin
RUN git clone https://github.com/jschanz/hacomfoairmqtt.git
WORKDIR hacomfoairmqtt


RUN mkdir -p /opt/hacomfoairmqtt
COPY src/ca350.py /opt/hacomfoairmqtt/ca350.py
COPY src/config.ini.docker /opt/hacomfoairmqtt/config.ini.docker

COPY src/start.sh /usr/local/bin/start.sh
RUN chmod 744 /usr/local/bin/start.sh
CMD /usr/local/bin/start.sh


# Copy data for add-on
COPY run.sh /
RUN chmod a+x /run.sh

CMD [ "/run.sh" ]



