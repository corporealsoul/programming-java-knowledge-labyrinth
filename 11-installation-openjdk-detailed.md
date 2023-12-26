
### OpenJDK Installation — Detailed

#### Download required file,

Open JDK Site address : https://adoptium.net/temurin/releases/


`[anup@c9-250-server ~]$ sudo dnf update`

`[anup@c9-250-server ~]$ sudo dnf install epel-release epel-next-release`

#### Extract,

`[anup@c9-250-server ~]$ ls -ltr`

`[anup@c9-250-server ~]$ tar -xvzf OpenJDK19U-jdk_x64_linux_hotspot_19_36.tar.gz`

#### Configure,

`[anup@c9-250-server ~]$ ls -ltr`

`[anup@c9-250-server ~]$ ln -sf jdk-19+36/ java-19`

`[anup@c9-250-server ~]$ ls -ltr`

`[anup@c9-250-server ~]$ cd java-19/`

`[anup@c9-250-server java-19]$ pwd`

    /home/anup/java-19
   
`[anup@c9-250-server java-19]$ ls -ltr`

`[anup@c9-250-server java-19]$ nano ~/.bash_profile`

    # .bash_profile
    
    # Get the aliases and functions
    #if [ -f ~/.bashrc ]; then
    #       . ~/.bashrc
    #fi
    
    # User specific environment and startup programs
    
    # .bash_profile
    
    # Get the aliases and functions
    if [ -f ~/.bashrc ]; then
            . ~/.bashrc
    fi
    
    # User specific environment and startup programs
    
    export JAVA_HOME=/home/anup/java-19
    
    PATH=${JAVA_HOME}:${JAVA_HOME}/bin:${JAVA_HOME}/lib:$PATH:$HOME/bin
    
    export PATH
    
    
    
#### Run and verify,

`[anup@c9-250-server java-19]$ source ~/.bash_profile`

`[anup@c9-250-server java-19]$ java -version`

`[anup@c9-250-server java-19]$ javac -version`

`[anup@localhost java-11]$ echo $JAVA_HOME`
