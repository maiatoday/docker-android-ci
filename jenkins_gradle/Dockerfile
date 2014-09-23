#
# maiatoday/jenkins_cmake
#

FROM jenkins_cmake
MAINTAINER maiatoday <maiatoday@gmail.com>

USER root

# Install Gradle
RUN wget https://services.gradle.org/distributions/gradle-2.0-bin.zip
RUN unzip gradle-2.1-bin.zip
RUN mv gradle-2.1 /opt/
RUN rm gradle-2.1-bin.zip

# Environment variables
ENV GRADLE_HOME /opt/gradle-2.1
ENV PATH $PATH:$GRADLE_HOME/bin

USER jenkins

