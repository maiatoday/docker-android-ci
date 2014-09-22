#
# maiatoday/jenkins_cmake
#

FROM jenkins
MAINTAINER maiatoday <maiatoday@gmail.com>

USER root
RUN apt-get update && apt-get clean
RUN apt-get install -y cmake 
USER jenkins

#ENTRYPOINT ["java", "-jar", "/opt/jenkins.war"]
#EXPOSE 8080
#CMD [""]
