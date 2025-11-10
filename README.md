<h2>create an ec2 instance</h2>
<li>name the instance maven-deploy</li>
<li>select a key pair or create a new one</li>
<li>select a vpc and ensure the vpc is seating on a public subnet and also enable auto assign public ip</li>
<li>at the level of networking, open port 8080</li>
<h2>add a repository with a Maven package</h2>

```
 sudo yum install wget
```

```
sudo wget https://repos.fedorapeople.org/repos/dchen/apache-maven/epel-apache-maven.repo -O /etc/yum.repos.d/epel-apache-maven.repo
```
<h2>set the version number for the packages</h2>

```
sudo sed -i s/\$releasever/6/g /etc/yum.repos.d/epel-apache-maven.repo
```
<h2>install apache maven</h2>

```
sudo yum install -y apache-maven
```
<h2>install Java 8 on your EC2 instance</h2>

```
sudo yum install java-1.8.0-devel -y

```
```
sudo yum install java-11 -y

```
<h2>set Java 8 as the default runtime on your EC2 instance</h2>
```
sudo /usr/sbin/alternatives --config java

```
<li> When prompted, enter the number corresponding (4) to java 1.8 for Java 11</li>
<h2>set Java 8 as the default compiler on your EC2 instance</h2>

```
sudo /usr/sbin/alternatives --config javac

```
<li>When prompted, enter the number 2 for Javac maven compiler</li>
<h2>review the config</h2>

```
mvn -v

```
<h2>install tree</h2>

```
sudo yum install tree -y

```
<h2>install git</h2>
```
sudo yum install git -y

```
<h2>Create the .m2 directory in the home directory of your current user</h2>
```
mkdir ~/.m2

```
<h2>this repository contains the java application</h2>
```
git clone https://github.com/asaphdanchi/practice-mvn-nexus-sonar-101.git

```

```
ls

```
```
cd into the directory

```
```
cd into java web to make sure you're in the pom.xml path

```
<h2>run the following maven commands</h2>
```
mvn validate

```
```
mvn compile

```
```
mvn test

```
```
mvn package

```
```
mvn verify

```
<h2>deploying the maven application</h2>
```
java -jar appname.jar

```
