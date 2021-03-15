The agent can execute system commands in sync or detached mode, thus translating a command from REST API to a system command.

It also can be used as an agent to control SUT (integration testing) during the test session as it is a multi-platform service and the binaries are available for:
- Windows
- Linux
- Raspbian

Some use cases are documented in [wiki](https://github.com/estuaryoss/estuary-agent/wiki).

Let's start the agent service and instruct it to register to the eureka server registry:  
`docker run -d --name=agent-direct -p 8082:8080 -e HTTP_AUTH_TOKEN=None -e EUREKA_SERVER=http://[[HOST_IP]]:8080/eureka/v2 -e APP_IP_PORT=[[HOST_IP]]:8082 estuaryoss/agent-go:4.2.0`{{execute}}

Let's verify that the agent service started:  
`curl -H Token:None http://[[HOST_IP]]:8082/about | json_pp`{{execute}} 

Let's list again the eureka apps, and see both services registered:  
`curl http://[[HOST_IP]]:8081/eurekaapps | json_pp`{{execute}}

Let's have a look over the logging, all estuary stack is implementing the same logging format:  
`docker logs agent-direct`{{execute}}  

It logs all API/startup messages and enriches HTTP requests and responses with OS details and other useful information.  

Two services are registered now in Eureka:
 - discovery
 - agent
 
https://[[HOST_SUBDOMAIN]]-8080-[[KATACODA_HOST]].environments.katacoda.com/eureka

For more info about the features and configuration, please visit [estuary agent](https://github.com/estuaryoss/estuary-agent).  
The python version won't be maintained anymore, only [go](https://github.com/estuaryoss/estuary-agent-go) and [java](https://github.com/estuaryoss/estuary-agent-java), but still can serve as documentation for the Agent configurations.
