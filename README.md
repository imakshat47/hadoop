# hadoop

sudo apt install default-jdk default-jre -y
apt install openssh-server openssh-client -y

sudo adduser hadoop; su - hadoop

ssh-keygen -ty rsa

cat ~/.ssh/id_rsa.pub >> ~/.ssh/authorized_keys
chmod 640 ~/.ssh/authorized_keys
ssh localhost

wget https://downloads.apache.org/hadoop/common/hadoop-3.3.1/hadoop-3.3.1.tar.gz

tar -xvzf hadoop-3.3.1.tar.gz; mv hadoop-3.3.1 hadoop

vi ~/.bashrc

# Hadoop Config
export JAVA_HOME=/usr/lib/jvm/zulu8/jre/bin/java
export HADOOP_HOME=/home/hadoop/hadoop
export HADOOP_INSTALL=$HADOOP_HOME
export HADOOP_MAPRED_HOME=$HADOOP_HOME
export HADOOP_COMMON_HOME=$HADOOP_HOME
export HADOOP_HDFS_HOME=$HADOOP_HOME
export YARN_HOME=$HADOOP_HOME
export HADOOP_COMMON_LIB_NATIVE_DIR=$HADOOP_HOME/lib/native
export PATH=$PATH:$HADOOP_HOME/sbin:$HADOOP_HOME/bin
export HADOOP_OPTS="-Djava.library.path=$HADOOP_HOME/lib/native"

 source ~/.bashrc
 
 hdfs namenode -format
 start-all.sh
 jps
