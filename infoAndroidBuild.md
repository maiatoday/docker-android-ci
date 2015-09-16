# make an android build server in a docker image

* use standard jenkins docker image, it already has java 7 in it.
* add android SDK
    http://dertompson.com/2014/09/01/jenkins-in-a-docker-container/
    http://blog.zuehlke.com/en/configure-your-android-project-on-jenkins/
* add plugins
   git, gradle, android emulator?
* pull in git project

* setup a new item


# run run jenkins server for the first time
```
    mkdir /home/username/data/jenkins -p
    sudo chown 102 /home/username/data/jenkins
    docker run --name reach_jenkins -d -p 8080:8080 -v /home/username/data/jenkins:/var/jenkins_home jenkins
```

# start/stop jenkins server
```
    docker start reach_jenkins
    docker stop reach_jenkins
```
# Connect to the jenkins server
In the browser goto http://localhost:8080



# docker installation
https://docs.docker.com/installation
