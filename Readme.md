# EGA.Data.API.v3.EUREKA

This is a standalone Spring Eureka server. It is configured to run on port 8761. The correct URL to this service must be specified in all micro services using the Eureka discovery server.

There are no dependencies.

All micro services will register themselves (using their `"spring.application.name={app.name}"`) with Eureka. URLs for REST calls between microservices can then be specified as `"http(s)://{app.name}/"`. The Spring REST template automatically contacts Eureka and resolves this to the correct URL for `{app.name}`. If multiple instances of service `{app.name}` are resistered with Eureka it will automatically perform Ribbon load balancing.

This allows for easy setup, configuration, and deployment of micro services. It also allows for easy replication of services to deal with increased demands or to improve resilience. Rest calls between micro services can now be coded using eah services's name, without having to provide an accurate list of deployed URLs.
