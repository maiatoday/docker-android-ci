#
# maiatoday/buildgcc
#

FROM ubuntu:14.04
MAINTAINER maiatoday <maiatoday@gmail.com>

USER root
RUN apt-get update && apt-get clean
RUN apt-get install -y build-essential cmake 
RUN apt-get install -y libgtest-dev
RUN cd /usr/src/gtest && cmake CMakeLists.txt && make && cp *.a /usr/lib

