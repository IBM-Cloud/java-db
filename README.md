# Java DB Sample

The Java DB Web Starter demonstrates how to use JPA with the Bluemix SQL Database service. The application displays a list of persisted items and lets the user add, modify, or delete them. The UI calls a RESTful CRUD API (/api/todolist) to retrieve, add and remove items.

## Decomposition

* See src/main/java/example/jpa/TODOListResource.java for the item CRUD API and obtaining the EntityManager
* See src/main/webapp/WEB-INF/web.xml & src/main/resources/META-INF/persistence.xml for JPA configuration
* See WebContent/index.js and WebContent/util.js for how the front-end UI calls the back-end API
