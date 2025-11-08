<h2>create an ec2 instance</h2>
<li>at the level of networking, open port 8080</li>

<h2>Install Apache Maven on your EC2 instance. First, enter the following to add a repository with a Maven package</h2>

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

The Gremlin libraries require Java 8. Enter the following to install Java 8 on your EC2 instance.

10. sudo yum install java-1.8.0-devel -y

10. sudo yum install java-11 -y

11. Enter the following to set Java 8 as the default runtime on your EC2 instance.

12. sudo /usr/sbin/alternatives --config java

13. When prompted, enter the number corresponding (4) to java 1.8 for Java 11.

14. Enter the following to set Java 8 as the default compiler on your EC2 instance.

15. sudo /usr/sbin/alternatives --config javac

16. When prompted, enter the number 2 for Javac maven compiler.

17. Make sure to review this config if mvn compile breaks

18. mvn -v

    sudo yum install tree -y

19. install git

20. sudo yum install git -y

21. Create the .m2 directory in the home directory of your current user

22. mkdir ~/.m2

this repository contains the java application
23. git clone https://github.com/asaphdanchi/practice-mvn-nexus-sonar-101.git
    ls/
    cd into the directory
    cd into java web to make sure you're in the pom.xml path
    mvn validate
    mvn compile
    mvn test
    mvn package
    mvn verify
    java -jar appname.jar

