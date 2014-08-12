#
# maiatoday/android-sdk
#

FROM maiatoday/androidSDK
MAINTAINER maiatoday <maiatoday@gmail.com>

#with thanks to Allan Espinosa <allan.espinosa@outlook.com>

RUN apt-get update && apt-get clean
ADD http://mirrors.jenkins-ci.org/war/1.575/jenkins.war /opt/jenkins.war
RUN chmod 644 /opt/jenkins.war
ENV JENKINS_HOME /jenkins

ENTRYPOINT ["java", "-jar", "/opt/jenkins.war"]
EXPOSE 8080
CMD [""]
