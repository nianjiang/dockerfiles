FROM oraclelinux

MAINTAINER Nian Jiang 

ADD jdk-6u45-linux-x64.bin /usr/local/
ADD jdk-7u80-linux-x64.tar.gz /usr/local/
ADD jdk-8u202-linux-x64.tar.gz /usr/local/
ADD jdk-9.0.4_linux-x64_bin.tar.gz /usr/local/

RUN cd /usr/local && sh /usr/local/jdk-6u45-linux-x64.bin && rm -rf /usr/local/jdk-6u45-linux-x64.bin 

ENV JAVA_6_HOME=/usr/local/jdk1.6.0_45 \
	JAVA_7_HOME=/usr/local/jdk1.7.0_80 \
	JAVA_8_HOME=/usr/local/jdk1.8.0_202 \
	JAVA_9_HOME=/usr/local/jdk-9.0.4 \
	JAVA_HOME=/usr/local/jdk1.8.0_202

ENV	CLASSPATH=.:$JAVA_HOME/lib/dt.jar:$JAVA_HOME/lib/tools.jar \
	PATH=$PATH:$JAVA_HOME/bin

RUN alternatives --install /usr/bin/java java $JAVA_HOME/bin/java 1 && \
    alternatives --install /usr/bin/jar  jar  $JAVA_HOME/bin/jar  1 && \
    rm -rf /tmp/*


CMD /bin/bash