# Java DB Sample
https://console.ng.bluemix.net/catalog/starters/java-db-web-starter/

The Java DB Web Starter demonstrates how to use JPA with the Bluemix SQL Database service. The application displays a list of persisted items and lets the user add, modify, or delete them. The UI calls a RESTful CRUD JAX-RS API (/api/todolist) to retrieve, add and remove items.

## Decomposition
**API - JAX-RS Resource**

See `src/main/java/example/jpa/TODOListResource.java` for the item CRUD API and obtaining the EntityManager.

**JPA Configuration**

See `src/main/webapp/WEB-INF/web.xml` & `src/main/resources/META-INF/persistence.xml` for JPA configuration.

**UI**

See `src/main/webapp/WEB-INF/index.html`, `src/main/webapp/WEB-INF/index.js` and `src/main/webapp/WEB-INF/util.js` for the front-end UI calling the back-end API.
