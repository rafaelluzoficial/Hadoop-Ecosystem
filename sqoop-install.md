Installation of Sqoop 1.4.7 in ubuntu 20

## Step 1: Verifying Java version
```bash
java -version

openjdk version "11.0.11" 2021-04-20
OpenJDK Runtime Environment (build 11.0.11+9-Ubuntu-0ubuntu2.20.04)
OpenJDK 64-Bit Server VM (build 11.0.11+9-Ubuntu-0ubuntu2.20.04, mixed mode, sharing)
```

## Step 2: Verifying Hadoop version
```bash
hadoop version

Hadoop 3.3.1
Source code repository https://github.com/apache/hadoop.git -r a3b9c37a397ad4188041dd80621bdeefc46885f2
Compiled by ubuntu on 2021-06-15T05:13Z
Compiled with protoc 3.7.1
From source with checksum 88a4ddb2299aca054416d6b7f81ca55
This command was run using /usr/local/hadoop/share/hadoop/common/hadoop-common-3.3.1.jar
```

## Step 3: Downloading Sqoop
http://archive.apache.org/dist/sqoop/1.4.7/
```bash
tar -xvf sqoop-1.4.7.bin__hadoop-2.6.0.tar.gz
su
password:

mv sqoop-1.4.4.bin__hadoop-2.0.4-alpha /usr/lib/sqoop
exit
```

## Step 4: Configuring bashrc
```bash
sudo gedit ~/.bashrc

#Sqoop
export SQOOP_HOME=/usr/lib/sqoop export PATH=$PATH:$SQOOP_HOME/bin
```
```bash
source ~/.bashrc
```

## Step 5: Configuring Sqoop
```bash
cd $SQOOP_HOME/conf
mv sqoop-env-template.sh sqoop-env.sh
```

Open sqoop-env.sh and edit the following lines
```bash
export HADOOP_COMMON_HOME=/usr/local/hadoop 
export HADOOP_MAPRED_HOME=/usr/local/hadoop
```

## Step 6: Download and Configure mysql-connector-java
http://ftp.ntu.edu.tw/MySQL/Downloads/Connector-J/
```bash
tar -zxf mysql-connector-java-5.1.30.tar.gz
su
password:

cd mysql-connector-java-5.1.30
mv mysql-connector-java-5.1.30-bin.jar /usr/lib/sqoop/lib
```

## Step 7: Verifying Sqoop
```bash
cd $SQOOP_HOME/bin
sqoop-version

2021-11-13 12:57:50,180 INFO sqoop.Sqoop: Running Sqoop version: 1.4.7
Sqoop 1.4.7
git commit id 2328971411f57f0cb683dfb79d19d4d19d185dd8
Compiled by maugli on Thu Dec 21 15:59:58 STD 2017
```
