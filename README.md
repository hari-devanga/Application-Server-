# Application-Server-

If you go and use yum install tomcat it will not work

You must go to this path wget - https://dlcdn.apache.org/tomcat/

wget https://dlcdn.apache.org/tomcat/tomcat-9/v9.0.91/bin/apache-tomcat-9.0.91.tar.gz

copy this path in your host machine and just run it -it will install tomcat

But this will be in zip format so you must unzip by using this command  :-  tar -zvxf apache-tomcat-9.0.91.tar.gz

apache runs on java so install java :-  yum install-11 -y

 go to this path  to start the services :----

:-   cd /home/ec2-user/apache-tomcat-9.0.91/bin/

 run this  :    ./startup.sh

 now this application will be running in server 

 now to use manager app and host manager app we need to edit this files

 /home/ec2-user/apache-tomcat-9.0.91/webapps/host-manager/META-INF    and edit context.xml file rempve the two lines valve..

/home/ec2-user/apache-tomcat-9.0.91/webapps/manager/META-INF          and edit context.xml file rempve the two lines valve..

/home/ec2-user/apache-tomcat-9.0.91/conf/tomcat-users.xml file

add this below commands

<role rolename="manager-gui"/>
<role rolename="manager-script"/>
<role rolename="manager-jmx"/>
<role rolename="manager-status"/>
<user username="admin" password="admin" roles="manager-gui, manager-script, manager-jmx, manager-status"/>
<user username="deployer" password="deployer" roles="manager-script"/>
<user username="tomcat" password="s3cret" roles="manager-gui"/>  

done now you can access the application

 
