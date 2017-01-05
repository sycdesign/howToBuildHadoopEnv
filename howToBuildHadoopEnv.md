Step1:准备Linux环境

window环境安装虚拟机或者租用云主机

Step2:安装JDK，设置环境变量

    javac
    apt-get install openjdk7.jdk
    javac
    vim /etc/profile
        export JAVA_HOME=/usr/lib/jvm/java-7-***
        export JRE_HOME=$JAVA_HOME/jre
        export CLASSPATH=$JAVA_HOME/lib:$JRE_HOME/lib:$CLASSPATH
        export PAHT=$JAVA_HOME/bin:$JRE_HOME/bin:$PAHT
    :wq  
    source /etc/profile
    javac

Step3:如何配置Hadoop

    wget http://mirror.bit.edu.cn/apache/hadoop/common/hadoop-1.2.1/hadoop-1.2.1.tar.gz
    ls
    mv hadoop-1.2.1 /opt/
    ls
    tar -zxvf hadoop-1.2.1.tar.gz
    ls
    cd hadoop-1.2.1
    cd conf/
    配置四个文件mapred-site.xml core-site.xml hdfs-site.xml hadoop-env.sh

    vim hadoop-env.sh 

        echo $JAVA_HOME 
        修改文件
        ——————————————————————————————————————————————————————————————————————————
        # Set Hadoop-specific environment variables here.

        # The only required environment variable is JAVA_HOME.  All others are
        # optional.  When running a distributed configuration it is best to
        # set JAVA_HOME in this file, so that it is correctly defined on
        # remote nodes.

        # The java implementation to use.  Required.
        export JAVA_HOME=/usr/java/jdk1.7.0_71
        —————————————————————————————————————————————————————————————————————————————
    vim core-site.xml
        ______________________________________________________________________________

        <?xml version="1.0"?>
        <?xml-stylesheet type="text/xsl" href="configuration.xsl"?>

        <!-- Put site-specific property overrides in this file. -->

        <configuration>
            <property>
            <name>hadoop.tmp.dir</name>
            <value>/hadoop</value>
            </property>

            
        </configuration>
        ______________________________________________________________________________










