
### OracleJDK Installation — RPM

**Site address :** [Java Downloads | Oracle](https://www.oracle.com/java/technologies/downloads/ "https://www.oracle.com/java/technologies/downloads/")

`[anup@c9-250-server ~]$ sudo dnf update`

`[anup@c9-250-server ~]$ sudo dnf install epel-release epel-next-release`

**Download the required file,** 

`[anup@c9-250-server ~]$ wget https://download.oracle.com/java/19/latest/jdk-19_linux-x64_bin.rpm`

`[anup@c9-250-server ~]$ ls -ltr`

**Install the required package using the following command,** 

`[anup@c9-250-server ~]$ ls -ltr`

`[anup@c9-250-server ~]$ sudo rpm -ivh jdk-19_linux-x64_bin.rpm`

`[anup@c9-250-server ~]$ java -version`

`[anup@c9-250-server ~]$ javac -version`

**Setting up $JAVA_HOME and $PATH,** 

`[anup@c9-250-server ~]$ rpm -q --whatprovides java`

`[anup@c9-250-server ~]$ update-alternatives --config java`

`[anup@c9-250-server ~]$ export JAVA_HOME=/usr/lib/jvm/jdk-19-oracle-x64/`

`[anup@c9-250-server ~]$ echo $JAVA_HOME`

`[anup@c9-250-server ~]$ export PATH=$PATH:/usr/lib/jvm/jdk-19-oracle-x64/bin`

`[anup@c9-250-server ~]$ echo $PATH`
