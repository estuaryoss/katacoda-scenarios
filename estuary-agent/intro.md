This is estuary agent, a powerful and flexible agent which can be used as:
- remote command executor
- exposing CLI app through REST API
- controlling the test automation framework (maven/python, etc)
- integration testing by controlling and configuring the SUT

Some use cases are explained [here](https://github.com/dinuta/estuary-agent/wiki).

Before starting the scenario, please read the high-level description of the agent [here](https://dinuta.github.io/estuary-agent).  

In this scenario you will learn about executing multiple commands in different modes:
- sequential 
- parallel 
- background

Before starting this scenario you must know about:
- testing / developing REST API microservices
- JSON 
- HTTP protocol

Keep in mind that there are two implementations of the agent, both being multi-platform:
- [python](https://github.com/dinuta/estuary-agent), packaged as binary with pyinstaller 
- [java](https://github.com/dinuta/estuary-agent-java), packaged as an executable jar with artifacts deployed to maven central.

For more information please read the repo's [README.md](https://github.com/dinuta/estuary-agent/blob/master/README.md)
