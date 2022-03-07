FROM centos:7.5.1804
MAINTAINER "LY"

ADD jdk1.8.0_241  /opt/baq/jdk
ADD apache-tomcat-9.0.30 /opt/baq/tomcat

ENV JAVA_HOME=/opt/baq/jdk
ENV CLASSPATH=.:$JAVA_HOME/lib/dt.jar:$JAVA_HOME/lib/tools.jar:$CLASSPATH
ENV PATH=/sbin:$JAVA_HOME/bin:$PATH
ENV CATALINA_HOME=/opt/baq/tomcat/

WORKDIR $CATALINA_HOME

ADD dll /opt/baq/dll
COPY ld.so.conf /etc
RUN ldconfig

RUN localedef -c -f UTF-8 -i zh_CN zh_CN.utf8
ENV LC_ALL zh_CN.utf8

EXPOSE 8080

CMD /opt/baq/tomcat/bin/catalina.sh run
