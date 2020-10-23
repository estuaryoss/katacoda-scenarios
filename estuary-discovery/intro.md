Before starting the scenario, please read the high-level description and the motivation [here](https://dinuta.github.io). It should not take more than 10 minutes.  

In this scenario you will learn about:
- how to get the list of applications registered in Eureka
- how to send unicast messages to the agents through the discovery
- how to send a broadcast message to the agents through the discovery

Before starting, you must have experience with:
- docker & docker-compose
- testing / developing REST API microservices
- HTTP protocol

In the following steps you will interact with the discovery and leverage its features:
-  gets the applications registered in Eureka
-  controls the agents (unicast & broadcast)
-  gets the background commands which runs on the agents
-  gets the active deployments across the stack (covered by [this scenario](https://katacoda.com/dinuta/scenarios/estuary-stack))

The discovery supports logging (EFK stack) which is useful for observability and statistics.
