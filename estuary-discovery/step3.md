The agent can execute system commands in sync or detached mode, thus translating a command from REST API to a system command.

It also can be used as an agent to control SUT (integration testing) during the test session as it is a multi-platform service and the binaries are available for:
- Windows
- Linux
- Raspbian

Some use cases are documented in [wiki](https://github.com/dinuta/estuary-agent/wiki).

Let's start 3 agents and instruct them to register to the eureka server registry:  
`docker run -d --name=agent1 -p 8082:8080 -e EUREKA_SERVER=http://[[HOST_IP]]:8080/eureka/v2 -e APP_IP_PORT=[[HOST_IP]]:8082 -e HTTP_AUTH_TOKEN=None estuaryoss/agent-go:4.2.1`{{execute}}

`docker run -d --name=agent2 -p 8083:8080 -e EUREKA_SERVER=http://[[HOST_IP]]:8080/eureka/v2 -e APP_IP_PORT=[[HOST_IP]]:8083 -e HTTP_AUTH_TOKEN=None estuaryoss/agent-go:4.2.1`{{execute}}

`docker run -d --name=agent3 -p 8084:8080 -e EUREKA_SERVER=http://[[HOST_IP]]:8080/eureka/v2 -e APP_IP_PORT=[[HOST_IP]]:8084 -e HTTP_AUTH_TOKEN=None estuaryoss/agent-go:4.2.1`{{execute}}

Let's verify that all three agents started:  
`curl -H 'Token:None' http://[[HOST_IP]]:8082/about | json_pp`{{execute}}
 
`curl -H 'Token:None' http://[[HOST_IP]]:8083/about | json_pp`{{execute}} 

`curl -H 'Token:None' http://[[HOST_IP]]:8084/about | json_pp`{{execute}} 

Let's list again the eureka apps, and see 4 services registered:  
`curl -H 'Token:None' http://[[HOST_IP]]:8081/eurekaapps | json_pp > eureka_apps.json `{{execute}}

Let's have a look over the logging, all estuary agents are implementing the same logging format:  
`docker logs agent1`{{execute}}  

It logs all API/startup messages and enriches HTTP requests and responses with OS details and other useful information.  

Four services are registered now in Eureka:
 - 1 discovery
 - 3 agents
 
https://[[HOST_SUBDOMAIN]]-8080-[[KATACODA_HOST]].environments.katacoda.com/eureka

For more info about the features and configuration, please visit [estuary agent](https://github.com/dinuta/estuary-agent).
