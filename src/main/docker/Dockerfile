FROM openjdk:8-jdk
LABEL maintainer="amedrano@lst.tfo.upm.es"
#ENV JAVA_HOME /usr/lib/jvm/java-8-openjdk-amd64

## To use Apache as proxy (for example to add tls tunneling, see apache.conf file) un-comment the next block (and switch CMD statement)
##install apache and add proxies
#RUN apt-get update && apt-get install -y --no-install-recommends apache2 && \
#	a2enmod proxy && a2enmod proxy_http && \
#	rm -rf /etc/apache2/sites-enabled/*
#COPY ./apache.conf /etc/apache2/sites-available/uaal.conf
#
#COPY ./apache.conf /etc/apache2/sites-enabled/uaal.conf 

RUN mkdir /uAAL
COPY assembly/ /uAAL/

#RUN ls -lha /uAAL/
#RUN chmod +x /uAAL/bin

VOLUME ["/uAAL/data"]
VOLUME ["/uAAL/etc"]
VOLUME ["/uAAL/deploy"]

EXPOSE 8081 9000
#TODO expose uAAL discovering and peering ports
#EXPOSE 1099 8101 44444 # Karaf ports

RUN sed -i "21s/out/stdout/" /uAAL/etc/org.ops4j.pax.logging.cfg;

CMD ["/uAAL/bin/karaf"]
# When using Apache use the following instead
#CMD service apache2 start && /uAAL/bin/karaf
