

### Pre-requisites
1. JDK
2. Tomcat
3. Maven

### Install apache tomcat 
```
sudo apt install tomcat9 tomcat9-admin
sudo service tomcat9 stop
sudo vi /etc/tomcat9/server.xml
sudo service tomcat9 restart

sudo apt install maven
```
Access and verify

### Create Add requirements
1. Dashboard > Manage Jenkins > Global Tool Configuration 
2. Scroll down to JDK, click JDK Installations
3. Add JDK, give a name and location of JAVA_HOME
4. Similarly ensure Git and Maven details are in place (follow instructor)
