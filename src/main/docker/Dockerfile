FROM openjdk:8-jdk
LABEL maintainer="amedrano@lst.tfo.upm.es"
#ENV JAVA_HOME /usr/lib/jvm/java-8-openjdk-amd64

RUN mkdir /uAAL
COPY assembly/ /uAAL/

RUN ls -lha /uAAL/

VOLUME ["/uAAL/data"]
VOLUME ["/uAAL/etc"]
VOLUME ["/uAAL/deploy"]

EXPOSE 8081 9000
#TODO expose uAAL discovering and peering ports
#EXPOSE 1099 8101 44444 # Karaf ports

RUN sed -i "21s/out/stdout/" /uAAL/etc/org.ops4j.pax.logging.cfg;

CMD ["/uAAL/bin/karaf"]
