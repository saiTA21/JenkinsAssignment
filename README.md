# JenkinsAssignment

## Steps to be followed
1) Create a Dockerfile to run Jenkins as a container.
2) Build the Dockerfile with the command  *Sudo Docker build -t <image-name> .*
3) Volume mount and Port Map of the Jenkins container with the local host with the command *docker run -it -p 8080:8080 -p 50000:50000 -v jenkins_home:/var/jenkins_home -v /var/run/docker.sock:/var/run/docker.sock --restart unless-stopped   <docker image> *
4) Now you can access the Jenkins with the *localhost:8080* in your laptop.
5) Now create a Github public repository with the Java files and Pom.xml file in it.
6) Next is to create a Jenkins freestyle project and configure the build steps.
7) Configuring the build steps:
    a) elect source Code Management (or SCM for short), select Git, add the remote Git repository URL of the project, and leave        the branch field empty so any commit made to any branch triggers our entire Jenkins process.
    b) Configure the GitHub project and add the project URL
    c) Configure Build Triggers accordingly. (select Poll SCM, which checks whether we made changes and then rebuilds our               project).
    d) In the Build window, add two Invoke top-level Maven targets steps.
8) BUild the project.
![Screenshot (8)](https://github.com/saiTA21/JenkinsAssignment/assets/152283229/a70443a2-fd8b-4719-aa52-88bcc7ec4870)
9) Now in order to contanerize the Java application which we built, create another Dockerfile.
10) Add this Dockerfile to Github and this should automatically start the build process in Jenkins.
11) Create an account in DockerHub and login to DockerHub inside Jenkins Conatainer.
12) Now add a build step of Docker Build and Publish Repository name: <your repo> /<docker-image>
13) Build the project again.
![Screenshot (10)](https://github.com/saiTA21/JenkinsAssignment/assets/152283229/08eea51a-1a49-488f-8656-6b01e7fd750c)
14) Now Check your DockerHub a new image of our Java application will be added.
![Screenshot (9)](https://github.com/saiTA21/JenkinsAssignment/assets/152283229/07e75063-dd97-439e-9b95-b87e0de960dd)





