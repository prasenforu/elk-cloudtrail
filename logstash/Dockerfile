FROM logstash

COPY logstash.conf /opt/
COPY logstash-codec-cloudtrail-3.0.0.gem /opt/
RUN /usr/share/logstash/bin/logstash-plugin install /opt/logstash-codec-cloudtrail-3.0.0.gem

CMD ["-f", "/opt/logstash.conf"]