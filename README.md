This repo contains various Dockerfiles used to mess around with making a ci servier.


I have been looking at various published docker files on registry.hub.docker.com in the hope of finding some version of this that is usable to me.

A jenkins server that can build c++ with cmake or gradle uses this sequence to build an image derived from the official jenkins build:

    docker build -t maiatoday/jenkins_cmake jenkins_cmake/
    docker build -t maiatoday/jenkins_gradle jenkins_gradle/

Set up a directory for the volume and run this image like this for the first time:
    mkdir /home/username/data/jenkins -p
    chown 102 /home/username/data/jenkins
    docker run --name myjenkins -p 8080:8080 -v /home/maia/data/jenkins:/var/jenkins_home maiatoday/jenkins_cmake

Stop and start the image like this:
    docker stop myjenkins
    docker start myjenkins

The android ci is still a work in progress

So the sequence could look like this:

    docker build -t maiatoday/java7 java7/
    docker build -t maiatoday/androidSDK androidSDK/
    docker build -t maiatoday/jenkins jenkins/ #I should try to use the official jenkins build

Then when you are done run up the final machine like this:
    docker run -d -P maiatoday/jenkins 
And then use docker ps to see the port to connect to in the browser.
    
I drew some inspiration from these docker files https://registry.hub.docker.com/u/oreomitch/jenkins-android/dockerfile
https://registry.hub.docker.com/repos/kemitix/
