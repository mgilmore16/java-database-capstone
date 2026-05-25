This Spring Boot application uses both MVC and REST controllers. Thymeleaf templates are used for the Admin and Doctor dashboards, while REST APIs serve all other modules. The application interacts with two databases—MySQL (for patient, doctor, appointment, and admin data) and MongoDB (for prescriptions). All controllers route requests through a common service layer, which in turn delegates to the appropriate repositories. MySQL uses JPA entities while MongoDB uses document models.



1. User accesses AdminDashboard or Appointment pages.  These pages will be built with Thymeleaf templates which render standard HTML to the browser.  These pages will interact with backend APIs using HTTP and JSON.
2. The action is routed to the appropriate Thymeleaf or REST controller.  MVC controllers will render Thymeleaf templates.  REST Controllers will process inputs from the API clients and produce JSON reposnes.
3. The controller calls the service layer.  The Controller layer is where business logic resides.  It is where validation logic and application logic is enforced.  Controllers orchestrate the flow.
4. Repository layer.  This is the layer that interacts with the databases.  There will be repositories for accessing relational data in MySQL and a repository for non-SQL data in MongoDB, such as prescription documents.
5. Database layer.  MySQL will handle all the structured data, such as users, roles, and appointments.  MongoDB will handle the less-structured, flexible data such as prescriptions.
6. Model Binding.  For MySQL the repositories will use JPA entities annotated with @Entity.  For MongoDB the data is loaded into document objects annotated with @Document.
7. Application Models.  MVC flow will pass from MVC Controller to Thymeleaf templates which are rendered as dynamic HTML.  REST flows will use REST controllers that send and receive DTOs that are serialized to JSON.









