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
<code>sudo yum install java-1.8.0-devel -y</code>
<code>sudo yum install java-11 -y</code>
<h2>set Java 8 as the default runtime on your EC2 instance</h2>
<code.sudo /usr/sbin/alternatives --config java</code>
<li> When prompted, enter the number corresponding (4) to java 1.8 for Java 11</li>
<h2>set Java 8 as the default compiler on your EC2 instance</h2>
<code>sudo /usr/sbin/alternatives --config javac</code>
<li>When prompted, enter the number 2 for Javac maven compiler</li>
<h2>review the config</h2>
<code>mvn -v</code>
<h2>install tree</h2>
<code>sudo yum install tree -y </code>
<h2>install git</h2>
<code>sudo yum install git -y</code>
<h2>Create the .m2 directory in the home directory of your current user</h2>
<code>mkdir ~/.m2</code>
<h2>this repository contains the java application</h2>
<code>git clone https://github.com/asaphdanchi/practice-mvn-nexus-sonar-101.git</code>
<code>ls</code>
<code>cd into the directory</code>
<code>cd into java web to make sure you're in the pom.xml path</code>
<h2>run the following maven commands</h2>
<code>mvn validate</code>
<code>mvn compile</code>
<code>mvn test</code>
<code>mvn package</code>
<code>mvn verify</code>
<h2>deploying the maven application</h2>
<code>java -jar appname.jar</code>
