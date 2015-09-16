This repo contains various Dockerfiles used to mess around with making a ci servier.


I have been looking at various published docker files on registry.hub.docker.com in the hope of finding some version of this that is usable to me.

A jenkins server that can build c++ with cmake or gradle uses this sequence to build an image derived from the official jenkins build:
```
    docker build -t maiatoday/jenkins_cmake jenkins_cmake/
    docker build -t maiatoday/jenkins_gradle jenkins_gradle/
```

Set up a directory for the volume and run this image like this for the first time:
```
    mkdir /home/username/data/jenkins -p
    sudo chown 102 /home/username/data/jenkins
    docker run --name myjenkins -p 8080:8080 -v /home/username/data/jenkins:/var/jenkins_home maiatoday/jenkins_cmake
```

Stop and start the image like this:
```
    docker stop myjenkins
    docker start myjenkins
```

The android ci is still a work in progress

So the sequence could look like this:
```
    docker build -t maiatoday/java7 java7/
    docker build -t maiatoday/androidSDK androidSDK/
    docker build -t maiatoday/jenkins jenkins/ #I should try to use the official jenkins build
```
Then when you are done run up the final machine like this:
```
    docker run -d -P maiatoday/jenkins
```
And then use docker ps to see the port to connect to in the browser.

I drew some inspiration from these docker files https://registry.hub.docker.com/u/oreomitch/jenkins-android/dockerfile
https://registry.hub.docker.com/repos/kemitix/

----
## Some info on the android jenkins slave
It is based off this image https://registry.hub.docker.com/u/evarga/jenkins-slave/dockerfile/
Also it can run with the jenkins docker plugin: https://wiki.jenkins-ci.org/display/JENKINS/Docker+Plugin

This image has an ssh port at 22. It also has an android install sitting in /opt/android-sdk-linux.

To build the image from the docker file

```
docker build -t maiatoday/jenkins-slave-android jenkins-slave-android/
docker run --name jenkins-slave-android -v /home/username/android-sdk:/opt/android-sdk-linux maiatoday/jenkins-slave-android
```


To interact with the image directly
```
docker run -i -t maiatoday/jenkins-slave-android /bin/bash
```

## Nodejs docker file

```
docker build -t maiatoday/nodejs-simple nodejs/
docker run --name mynodejs -d -v /home/username/projectroot:/project maiatoday/nodejs-simple cd /project && npm install
```
