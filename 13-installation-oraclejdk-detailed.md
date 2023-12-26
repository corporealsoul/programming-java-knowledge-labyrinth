
### OracleJDK Installation — Detailed

Download the Latest Java LTS Free : https://www.oracle.com/java/technologies/downloads/

**Download the required file,**

`[anup@c9-250-server ~]$ wget https://download.oracle.com/java/17/latest/jdk-17_linux-x64_bin.tar.gz`

`[anup@c9-250-server ~]$ ls -ltr`

**Install the required package,**

`[anup@c9-250-server ~]$ tar -xvzf jdk-17_linux-x64_bin.tar.gz`

`[anup@c9-250-server ~]$ ls -ltr`

`[anup@c9-250-server ~]$ ln -sf jdk-17.0.5/ java-17`

`[anup@c9-250-server ~]$ ls -ltr`

`[anup@c9-250-server ~]$ cd java-17/`

`[anup@c9-250-server java-17]$ pwd`

    /home/anup/java-17

`[anup@c9-250-server java-17]$ ls -ltr`

`[anup@c9-250-server java-17]$ nano ~/.bash_profile`

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
    
    export JAVA_HOME=/home/anup/java-17
    
    PATH=${JAVA_HOME}:${JAVA_HOME}/bin:${JAVA_HOME}/lib:$PATH:$HOME/bin
    
    export PATH
    

`[anup@c9-250-server java-17]$ source ~/.bash_profile`

`[anup@c9-250-server ~]$ java -version`

`[anup@c9-250-server ~]$ javac -version`

`[anup@c9-250-server ~]$ update-alternatives --config java`

`[anup@c9-250-server ~]$ echo $JAVA_HOME`

`[anup@c9-250-server ~]$ echo $PATH`
