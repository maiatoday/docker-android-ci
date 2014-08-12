#
# maiatoday/java7
#

FROM ubuntu:14.04
MAINTAINER maiatoday <maiatoday@gmail.com>

#with thanks to Paul Cambell &lt;pcampbell@kemitix.net&gt;

#
# Contains:
#  - oracle-java-7
#

ENV DEBIAN_FRONTEND noninteractive

RUN sed &#39;s/main$/main universe/&#39; -i /etc/apt/sources.list
RUN apt-get update
RUN apt-get upgrade -y

RUN apt-get install -y software-properties-common python-software-properties
RUN add-apt-repository ppa:webupd8team/java -y

RUN apt-get update
RUN echo oracle-java7-installer shared/accepted-oracle-license-v1-1 select true | /usr/bin/debconf-set-selections

RUN apt-get install -y oracle-java7-installer

RUN echo "\n\
export JAVA_HOME=/usr/lib/jvm/java-7-oracle/\n\
export PATH=\$JAVA_HOME/bin:\$PATH" \
	>> /etc/profile
