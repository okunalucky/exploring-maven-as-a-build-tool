- Create an ec2 instance
- Name the instance maven-deploy
- Select a key pair or create a new one
- Select a vpc and ensure the vpc is seating on a public subnet and also enable auto assign public ip
- At the level of networking, open port 8080
- Add a repository with a Maven package

```sh
 sudo yum install wget
```

```sh
sudo wget https://repos.fedorapeople.org/repos/dchen/apache-maven/epel-apache-maven.repo -O /etc/yum.repos.d/epel-apache-maven.repo
```
-Set the version number for the packages

```sh
sudo sed -i s/\$releasever/6/g /etc/yum.repos.d/epel-apache-maven.repo
```
- Install apache maven

```sh
sudo yum install -y apache-maven
```
- Install Java 8 on your EC2 instance
```sh
sudo yum install java-1.8.0-devel -y
sudo yum install java-11 -y
```
- Set Java 8 as the default runtime on your EC2 instance
```sh
  sudo /usr/sbin/alternatives --config java
```
- When prompted, enter the number corresponding (4) to java 1.8 for Java 11
- Set Java 8 as the default compiler on your EC2 instance
```sh
  sudo /usr/sbin/alternatives --config javac</code>
```
- When prompted, enter the number 2 for Javac maven compiler
- Review the config
```sh
  mvn -v
```
- Install tree
```sh
sudo yum install tree -y
```
- Install git
```sh
sudo yum install git -y
```
- Create the .m2 directory in the home directory of your current user
```sh
mkdir ~/.m2
```
- This repository contains the java application
```sh
git clone https://github.com/asaphdanchi/practice-mvn-nexus-sonar-101.git
```
- cd into the directory and ensure you're in the pom.xml path
- Run the following maven commands
```sh
mvn validate
mvn compile
mvn test
mvn package
mvn verify
```
<h2>deploying the maven application</h2>
<code>java -jar appname.jar</code>
