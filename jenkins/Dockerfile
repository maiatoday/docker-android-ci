#
# maiatoday/android-sdk
#

FROM maiatoday/androidSDK
MAINTAINER maiatoday <maiatoday@gmail.com>

#with thanks to Allan Espinosa <allan.espinosa@outlook.com>

RUN apt-get update && apt-get clean
ADD http://updates.jenkins-ci.org/latest/jenkins.war /opt/jenkins.war
RUN chmod 644 /opt/jenkins.war
ENV JENKINS_HOME /jenkins

#add jenkins plugins androidSDK git gradle GitHub
RUN mkdir -p /jenkins/plugins
ADD http://updates.jenkins-ci.org/latest/android-emulator.hpi /jenkins/plugins/android-emulator.hpi
ADD http://updates.jenkins-ci.org/latest/git.hpi /jenkins/plugins/git.hpi
ADD http://updates.jenkins-ci.org/latest/github.hpi /jenkins/plugins/github.hpi
ADD http://updates.jenkins-ci.org/latest/gradle.hpi /jenkins/plugins/gradle.hpi

ENTRYPOINT ["java", "-jar", "/opt/jenkins.war"]
EXPOSE 8080
CMD [""]
