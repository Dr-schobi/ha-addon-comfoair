ARG BUILD_FROM
FROM $BUILD_FROM

WORKDIR /bin
RUN git clone git clone https://github.com/jschanz/hacomfoairmqtt.git
WORKDIR hacomfoairmqtt


# Copy data for add-on
COPY run.sh /
RUN chmod a+x /run.sh

CMD [ "/run.sh" ]
