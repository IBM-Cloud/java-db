# Java Liberty with SQL Database Sample

The Java DB sample demonstrates how to use JPA with a SQL service on Bluemix. The application displays a list of persisted items and lets the user add, modify, or delete them. The UI calls a RESTful CRUD JAX-RS API (/api/todolist) to retrieve, add and remove items.
d
## Running on Bluemix
```
mvn install
cf push PickAUniqueName -p target/JavaDBApp.war
```
Then, go to Bluemix dashboard and bind the Clear DB MySQL service to the application and restage!

## Running Locally

1) Either provide your own mysql database or follow the steps above to create a ClearDB mysql database on Bluemix.
1) Download and upzip WebSphere Liberty.
1) Download mysql-connector-java-5.1.32 from https://mvnrepository.com/artifact/mysql/mysql-connector-java/5.1.32 
and place it in `$LIBERTY_HOME/wlp/usr/shared/resources/mysql`. If `mysql` directory does not exist, create it.
1) Configure the data source in the `$LIBERTY_HOME/usr/servers/defaultServer/server.xml` file
```
	<dataSource id='mysql-datasource' jdbcDriverRef='mysql-driver' jndiName='jdbc/mydbdatasource'> 
 		<properties databaseName="xxxxxxxx" 
			user="xxxxxxxxx" 
			password='xxxxx'
			portNumber="xxxx" serverName="xxxxxxxxx" /> 
	</dataSource>
	
	<jdbcDriver id="mysql-driver" libraryRef="mysql-library" />

	<library id="mysql-library">
		<fileset dir="${shared.resource.dir}/mysql" includes="*.jar"/>
	</library>
```
1) Run `mvn install` and copy the `target/JavaDBApp.war` to `$LIBERTY_HOME/usr/servers/defaultServer/dropins`

## Decomposition
**API - JAX-RS Resource**

See `src/main/java/example/jpa/TODOListResource.java` for the item CRUD API and obtaining the EntityManager.

**JPA Configuration**

See `src/main/webapp/WEB-INF/web.xml` & `src/main/resources/META-INF/persistence.xml` for JPA configuration.

**UI**

See `src/main/webapp/WEB-INF/index.html`, `src/main/webapp/WEB-INF/index.js` and `src/main/webapp/WEB-INF/util.js` for the front-end UI calling the back-end API.
