# Getting Started With Hibernate
This is the study project, to get started with Hibernate, to understand ORM framework.<br/>
Hibernate is a ORM tool (Object Relational Mapping) <br/>
This project creates the table with one tuple in Oracle Database.
Basically, this project deals with saving the data to the database.

<hr>
<b>Description: </b> <br/>
Creating a table in the database and saving the tuples with the help of Object Relational Mapping Tool - Hibernate
<h4>Mapping</h4>
<table> 
<tr>
<td>Class</td>
<td>Relation/Table</td>
</tr>
<tr>
<td>Fields</td>
<td>Columns</td>
</tr>
<tr>
<td>Object</td>
<td>Tuple</td>
</tr>
</table>
   
<hr>
<b>Prerequisites</b><br/>
<li>Java</li>
<li>JDBC</li>
<li>MySQL or Oracle or any database</li>
<hr>
<li>Hibernate: 4.1.6</li> 
<li>Oracle: 12c</li> 
<li>Java: 1.8</li> 
<hr>
<h3> Steps Followed: </h3>
<li>Create a maven project, Select maven-archetype-quickstart as artifact-id [Make sure that maven is installed on your machine]</li>
<li>Add hibernate dependency in pom.xml. I have added 4.1.6.Final version of hibernate from <a href ='https://mvnrepository.com/'>Maven Repository</a></li>
<li>Add oracle jdbc dependency. I have added ojdbc7 jar. This jar can be downloaded from Oracle website.</li>
<br/>
<b><u>Important Note: </u></b><br/>
Since this is a Maven project and ojdbc7 is an external library, you have to add this jar in your local maven repository. <br/><br/>
<b>Steps to add Oracle JDBC driver in local Maven repository </b>
<li>Download the oracle jdbc jar file from Oracle official website</li>
<li>In terminal/command prompt Type the command: <br/>mvn install:install-file -Dfile=C:\\PATH To YOUR OJDBC7 JAR\\ojdbc7.jar -DgroupId=com.oracle -DartifactId=ojdbc7 -Dversion=12.1.0 -Dpackaging=jar</li>
<li>Add the dependency in pom.xml => GroupID: com.oracle, artifactId: ojdbc7, version: 12.1.0</li>
<li>Update the maven project </li>
<hr>
<b>Adding Hibernate Plugin in eclipse</b>
<li> Hibernate plugin is needed to create the configuration file of hibernate (hibernate.cfg.xml)
<li> Install hibernate plugin from Eclipse Marketplace. I have installed it from JBoss Tool 4.4.4 Final
<hr>
<li>If we want to connect to the database, we need to provide configuration.</li>
<li>Configuration is provided in hibernate.cfg.xml</li>
<li>Provide database dialect ,driver class, connection url, username and password in hibernate.cfg.xml file.</li><br/>
<b>Database Dialect:</b> Name of the database (Oracle, MySQL, etc)<br/>I have put, Oracle 10g as Oracle10gDialect works for oracle 12c<br/>
<b>Driver Class: </b> For Oracle => oracle.jdbc.driver.OracleDriver <br/>

<hr>
<b>When you are connecting with oracle, no need to mention the schema name so the connection URL looks like as below : </b>
<br/>
<p> jdbc:oracle:thin:@Hostname:port:SID </p>
<hr>
<li>To specify that this class [Mapped to Relation in database] is allowed to store its object in database, use @Entity annotation
<li>@Id is used for specifying primary key.
<li>To create table, specify the property name of hbm2ddl in hibernate.cfg.xml 
<hr>
Whenever you have to make changes to the database you have to follow ACID properties.
<hr>
<b>Procedure: <b/>
<li>Open a session</li>
<li>Begin a Transaction</li>
<li>Save the object using session object</li>
<li>Commit the transaction</li>
<li>Close a session</li>

<hr>
Hence, save() helps to save the data to database.



