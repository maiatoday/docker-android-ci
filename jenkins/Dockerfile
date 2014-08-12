#
# maiatoday/android-sdk
#

FROM maiatoday/androidSDK
MAINTAINER maiatoday &lt;maiatoday@gmail.com&gt;

#with thanks to Allan Espinosa &quot;allan.espinosa@outlook.com&quot;

RUN apt-get update &amp;&amp; apt-get clean
ADD http://mirrors.jenkins-ci.org/war/1.575/jenkins.war /opt/jenkins.war
RUN chmod 644 /opt/jenkins.war
ENV JENKINS_HOME /jenkins

ENTRYPOINT [&quot;java&quot;, &quot;-jar&quot;, &quot;/opt/jenkins.war&quot;]
EXPOSE 8080
CMD [&quot;&quot;]
