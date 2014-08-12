The goal is to make a series of Dockerfile files to build up a CI machine. Ideally later images can build on earlier images so the plan is to make an image with the latest android SDK and emulator. Then to add to this gradle and then git. That image will then be able to pull from a git repo and build and test a project. This will be the base image which can be used to add a ci server such as jenkins or a teamcity agent.

* java7/Dockerfile (Java7) or (openjdk7?)
* androidSDK/Dockerfile (androidSDK git)
* gradle/Dockerfile    -- maybe this one can be skipped because the build wrapper gets gradle
* jenkins/Dockerfile 


I have been looking at various published docker files on registry.hub.docker.com in the hope of finding some version of this that is usable to me.

So the sequence would look like this:

    docker build -t maiatoday/java7 java7
    docker build -t maiatoday/androidSDK androidSDK
    docker build -t maiatoday/jenkins jenkins

Then when you are done run up the final machine like this:
    docker run -d -P maiatoday/jenkins 
And then use docker ps to see the port to connect to in the browser.
    
I drew some inspiration from these docker files https://registry.hub.docker.com/u/oreomitch/jenkins-android/dockerfile
https://registry.hub.docker.com/repos/kemitix/
