This is estuary stack, a powerful and flexible stack which can be used as:
- distributed test infrastructure
- shared environments to develop & test
- standalone services, as agents for test & software remote control
- exposing your CLI app remotely over REST API

Before starting the scenario, please read the high-level description and the motivation [here](https://dinuta.github.io). It should not take more than 10 minutes.  

In this scenario you will learn about:
- how you can deploy a complete dev/test environment and interact with the services within
- how to leverage the power and the flexibility of the agent
- how to view the distributed infrastructure live with the power of eureka and estuary discovery 

Before starting, you must have experience with:
- docker & docker-compose
- testing / developing REST API microservices
- HTTP protocol

In the following steps you will interact with the stack and leverage its features, but shortly said the stack:
-  manages the deployments in docker or acting as a proxy node in front of a Kubernetes cluster.
-  controls test framework, CLI app, remote machines through estuary agent
-  offers an overview of the distributed infrastructure services / active deployments and tests through the discovery service 
 
The stack supports logging (EFK stack) which is useful for observability and statistics.
