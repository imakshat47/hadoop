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

source ~/.bashrc
 
 hdfs namenode -format
 start-all.sh
 jps
