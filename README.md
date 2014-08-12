The goal is to make a series of Dockerfile files to build up a CI machine. Ideally later images can build on earlier images so the plan is to make an image with the latest android SDK and emulator. Then to add to this gradle and then git. That image will then be able to pull from a git repo and build and test a project. This will be the base image which can be used to add a ci server such as jenkins or a teamcity agent.

* Dockerfile_java7 (Java7)
* Dockerfile_androidSDK (androidSDK git)
* Dockerfile_gradle   -- maybe this one can be skipped because the build wrapper gets gradle
* Dockerfile_jenkins


I have been looking at various published docker files on registry.hub.docker.com in the hope of finding some version of this that is usable to me.

So the sequence would look like this:

    docker build -t maiatoday/androidSDK Dockerfile_androidSDK
    docker build -t maiatoday/androidBuild Dockerfile_gradle
    docker build -t maiatoday/androidJenkins Dockerfile_jenkins
    
I drew some inspiration from these docker files https://registry.hub.docker.com/u/oreomitch/jenkins-android/dockerfile
https://registry.hub.docker.com/repos/kemitix/
