#
# maiatoday/jenkins_gradle
#

FROM maiatoday/jenkins_cmake
MAINTAINER maiatoday <maiatoday@gmail.com>

USER root

# Install Gradle
RUN wget https://services.gradle.org/distributions/gradle-2.2-bin.zip
RUN unzip gradle-2.2-bin.zip
RUN mv gradle-2.2 /opt/
RUN rm gradle-2.2-bin.zip

# Environment variables
ENV GRADLE_HOME /opt/gradle-2.2
ENV PATH $PATH:$GRADLE_HOME/bin

USER jenkins

