This is estuary agent, a powerful and flexible agent which can be used as:
- remote command executor
- exposing CLI app through REST API
- controlling the test automation framework (maven/python, etc)
- integration testing by controlling and configuring the SUT

Some use cases are explained [here](https://github.com/estuaryoss/estuary-agent/wiki).

Before starting the scenario, please read the high-level description of the agent [here](https://estuaryoss.github.io/pages/agent.html).  

In this scenario you will learn about executing multiple commands in different modes:
- sequential 
- parallel 
- background

Before starting this scenario you must know about:
- testing / developing REST API microservices
- JSON 
- HTTP protocol

Keep in mind that there are two implementations of the agent, both being multi-platform:
- [go](https://github.com/dinuta/estuary-agent-go), can be packaged as binary   
- [java](https://github.com/dinuta/estuary-agent-java), can be packaged as an executable jar with artifacts deployed to maven central  
- [python](https://github.com/dinuta/estuary-agent), can be packaged as binary with pyinstaller (won't be maintained in the future)  

For more information please read the repo's [README.md](https://github.com/estuaryoss/estuary-agent/blob/master/README.md)
