# make an android build server in a docker image

* use standard jenkins docker image, it already has java 7 in it.
* add android SDK
* add plugins
   git, gradle, android emulator?
* pull in git project

* setup a new item


# run run jenkins server for the first time
Install docker. The version at the time this doc was written is 1.8.2
```
    mkdir /home/username/data/jenkins -p
    sudo chown 102 /home/username/data/jenkins
    docker run --name my_jenkins -d -p 8080:8080 -v /home/username/data/jenkins:/var/jenkins_home maiatoday/jenkins_android
```

# start/stop jenkins server
```
    docker start my_jenkins
    docker stop my_jenkins
```
# Connect to the jenkins server
In the browser goto http://localhost:8080



# docker installation
https://docs.docker.com/installation

# useful links
    http://dertompson.com/2014/09/01/jenkins-in-a-docker-container/
    http://blog.zuehlke.com/en/configure-your-android-project-on-jenkins/
    http://www.vogella.com/tutorials/Jenkins/article.html
    https://github.com/jenkinsci/docker
