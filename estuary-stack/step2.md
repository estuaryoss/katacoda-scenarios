Discovery service will list all the applications registered in Eureka.

If it is deployed, the client should only interact with it to discover all the apps, thus no Eureka client needs to be implemented.

The discovery is also being able to list deployments from the deployers and the command sessions from the agents.

It also supports unicast and broadcast messages to the agents, making it very useful for:
- hard reproducible bugs -> broadcast command session with the same configuration
- distributed command sessions with different configurations > unicast message

Let's start the discovery service and instruct it to register to the Eureka server registry:  
`docker run -d --name=discovery-direct -p 8081:8080 -e EUREKA_SERVER=http://[[HOST_IP]]:8080/eureka/v2 -e APP_IP_PORT=[[HOST_IP]]:8081 estuaryoss/discovery:4.2.3`{{execute}}

Let's verify that the service started:  
`curl http://[[HOST_IP]]:8081/about | json_pp`{{execute}}  

Let's list eureka apps:  
`curl -i http://[[HOST_IP]]:8081/eurekaapps`{{execute}}   

Observe that every request has an associated X-Request-ID header. If it's set from the client side it will echo back the same.
This is useful for debugging purposes in a logging system, or tracking the request end-to-end if multiple services are chained (E.g. discovery will broadcast/unicast messages to the agents).

Now one service is registered in Eureka: 
https://[[HOST_SUBDOMAIN]]-8080-[[KATACODA_HOST]].environments.katacoda.com/eureka

For more info about the features and configuration, please visit [estuary-discovery](https://github.com/estuaryoss/estuary-discovery).

** [json_pp](https://manpages.ubuntu.com/manpages/trusty/man1/json_pp.1.html) prettifies the output, and it's already installed on Ubuntu distros
