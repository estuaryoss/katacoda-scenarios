The stack has Netflix eureka as its main server registry. This is a key requirement in a distributed infrastructure for service discovery from the client-side.

The deployers support clustering through Eureka, managed from the client-side opposed to other models where the clustering is controlled from the server-side.
This comes with flexibility, but forces the deployment logic algorithms (round-robin, resources-driven, etc) to be implemented on the client-side.

The client who interacts with the stack **should only implement** a Eureka client or just discover them directly from discovery service, if the discovery is deployed in the same eureka domain.

Implementing Eureka as the main service registry makes the stack compatible and deployable in the cloud.  

Let's boot up a custom and up-to-date eureka server registry:  
`docker run -d -p 8080:8080 estuaryoss/netflix-eureka:1.10.5`{{execute}}

Let's open a browser page to the server registry, to observe the registration of the services:  
https://[[HOST_SUBDOMAIN]]-8080-[[KATACODA_HOST]].environments.katacoda.com/eureka

** the browser might not display 100% the UI accurately, but it will show the registered services
