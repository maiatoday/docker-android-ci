#
# maiatoday/jenkins_cmake
#

FROM jenkins
MAINTAINER maiatoday <maiatoday@gmail.com>

USER root
RUN apt-get update && apt-get clean
RUN apt-get install -y build-essential cmake 
RUN apt-get install -y libgtest-dev
RUN cd /usr/src/gtest && cmake CMakeLists.txt && make && cp *.a /usr/lib
USER jenkins

#ENTRYPOINT ["java", "-jar", "/opt/jenkins.war"]
#EXPOSE 8080
#CMD [""]
