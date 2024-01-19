
Console:
========
Start "Perl (command line) [V5]"


Java Setup:
===========
Start "Perl (command line) [V5]"

set JAVA_HOME=C:\ProgramData\AppV\A454648B-9095-4AC1-99F6-CBF5BBDF051A\2D2550AA-8F33-4BDF-ADF3-F4C30397D7BC\Root\plugins\org.eclipse.justj.openjdk.hotspot.jre.full.win32.x86_64_17.0.4.v20220903-1038\jre

set PATH=%PATH%;%JAVA_HOME%\bin

java -version


Maven Setup:
============
@Java Setup

set MVN_HOME=D:\apache-maven-3.9.3

set "MAVEN_OPTS="

set PATH=%PATH%;%MVN_HOME%\bin

REM User Settings: C:\Users\COLOTPI\.m2\settings.xml
REM replace ... with current password
REM  <settings 
REM  	xmlns="http://maven.apache.org/SETTINGS/1.0.0" 
REM  	xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
REM   	xsi:schemaLocation="http://maven.apache.org/SETTINGS/1.0.0 https://maven.apache.org/xsd/settings-1.0.0.xsd">
REM   <!-- <localRepository/> -->
REM   <!-- <interactiveMode/> -->
REM   <!-- <offline/> -->
REM   <!-- <pluginGroups/> -->
REM   <!-- <servers/> OxygenXml maven repository -->
REM   <!-- <mirrors/> -->
REM   <proxies>
REM     <proxy>
REM       <id>httpproxy</id>
REM       <active>true</active>
REM       <protocol>http</protocol>
REM       <host>proxy-t2-bx.welcome.ec.europa.eu</host>
REM       <port>8012</port>
REM       <username>colotpi</username>
REM       <password>...</password>
REM       <nonProxyHosts>localhost,127.0.0.1</nonProxyHosts>
REM     </proxy>
REM     <proxy>
REM       <id>myhttpsproxy</id>
REM       <active>true</active>
REM       <protocol>https</protocol>
REM       <host>proxy-t2-bx.welcome.ec.europa.eu</host>
REM       <port>8012</port>
REM       <username>colotpi</username>
REM       <password>...</password>
REM       <nonProxyHosts>localhost,127.0.0.1</nonProxyHosts>
REM     </proxy>
REM   </proxies>
REM   <profiles>
REM     <profile>
REM       <repositories>
REM         <repository>
REM           <id>oxygenxml</id>
REM           <name>Oxygen XML</name>
REM           <releases>
REM             <enabled>true</enabled>
REM             <updatePolicy>always</updatePolicy>
REM             <checksumPolicy>warn</checksumPolicy>
REM           </releases>
REM           <snapshots>
REM             <enabled>true</enabled>
REM             <updatePolicy>never</updatePolicy>
REM             <checksumPolicy>fail</checksumPolicy>
REM           </snapshots>
REM           <url>https://www.oxygenxml.com/maven</url>
REM           <layout>default</layout>
REM         </repository>
REM         <repository>
REM           <id>central</id>
REM           <url>https://repo.maven.apache.org/maven2</url>
REM           <releases>
REM             <enabled>true</enabled>
REM           </releases>
REM         </repository>
REM       </repositories>
REM       <pluginRepositories>
REM         <pluginRepository>
REM           <id>central</id>
REM           <url>https://repo.maven.apache.org/maven2</url>
REM           <releases>
REM             <enabled>true</enabled>
REM           </releases>
REM         </pluginRepository>
REM       </pluginRepositories>
REM     </profile>
REM   </profiles>
REM   <!-- <activeProfiles/> -->
REM </settings>

mvn -v

REM example of project generation: mvn org.apache.maven.plugins:maven-archetype-plugin:2.4:generate -DarchetypeGroupId=com.oxygenxml.samples -DarchetypeArtifactId=oxygen-sdk-samples-archetype -DarchetypeVersion=25.1.0.2 -DgroupId=myGroup -DartifactId=mySample -Dversion=1.0-SNAPSHOT -DarchetypeRepository=https://www.oxygenxml.com/maven/

cd /D D:\OP\_DEV\QualityControlReports

cd .\modules\QualityControlReportsConfiguration

mvn clean compile site install

open ./target/site/index.html

verify if the QC package is still up-to-date

cd ..\..

mvn install

Usage:
======

Add in your Projects's POM :

    <parent>
        <groupId>lu.infeurope</groupId>
        <artifactId>QualityControlReports</artifactId>
        <version>1.3</version>
<!-- to avoid deploy in dev, and to link sites        <relativePath>../QualityControlReports/</relativePath> -->
    </parent>
	
and generate a full website for your application using 

mvn site





