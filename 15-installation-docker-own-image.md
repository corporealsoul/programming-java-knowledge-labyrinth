
### Get Java by Creating own image,

**Creating Ubuntu machine using Dockerfile,**

`[anup@c9-251-docker ~]$ nano Dockerfile`

    # ubuntu
    FROM ubuntu
    
    # Install OpenJDK-8
    RUN apt-get update && \
            apt-get install -y openjdk-8-jdk && \
            apt-get install -y ant && \
            apt-get clean && \
            rm -rf /var/lib/apt/lists/* && \
            rm -rf /var/cache/oracle-jdk8-installer;
    
    # Fix certificate issues, 
    RUN apt-get update && \
            apt-get install -y ca-certificates-java && \
            apt-get clean && \
            update-ca-certificates -f && \
            rm -rf /var/lib/apt/lists/* && \
            rm -rf /var/cache/oracle-jdk8-installer;
    
    # Setup JAVA_HOME -- useful for docker commandline
    ENV JAVA_HOME /usr/lib/jvm/java-8-openjdk-amd64/
    RUN export JAVA_HOME

`[anup@c9-251-docker ~]$ docker build -t java8-machine .`

`[anup@c9-251-docker ~]$ docker images`

`[anup@c9-251-docker ~]$ docker run -it java8-machine bash`

`root@decd5fdc4773:/# java -version`

<br>

**Creating CentOS machine using Dockerfile,**

`[anup@c9-251-docker ~]$ nano Dockerfile`

    FROM centos

    RUN cd /etc/yum.repos.d/
    RUN sed -i 's/mirrorlist/#mirrorlist/g' /etc/yum.repos.d/CentOS-*
    RUN sed -i 's|#baseurl=http://mirror.centos.org|baseurl=http://vault.centos.org|g' /etc/yum.repos.d/CentOS-*
    RUN yum -y update
    RUN yum -y install java-11-openjdk-devel

    # Setup JAVA_HOME -- useful for docker commandline
    ENV JAVA_HOME /usr/lib/jvm/java-11-openjdk-11.0.17.0.7-0.2.ea.el9.x86_64/
    RUN export JAVA_HOME

`[anup@c9-251-docker ~]$ docker build -t javaltst-centosmachine .`

`[anup@c9-251-docker ~]$ docker run -it javaltst-centosmachine bash`

`[root@04b0b9df693d /]# java -version`

`[root@04b0b9df693d /]# echo $JAVA_HOME`

`[root@04b0b9df693d /]# exit`

<br>

`[anup@c9-251-docker ~]$ docker commit 04b0b9df693d java-image`

    sha256:69a5278aa19302e4a36460a187b99cdbef6193412f0bce0188bb6f24e73c95c2

`[anup@c9-251-docker ~]$ docker run -it java-image bash`

`[root@264961a7d856 /]# java -version`

`[root@264961a7d856 /]# echo $JAVA_HOME`
