To be able to control the machine over REST API you must deploy the Agent.

Download the binary (platform specific)    
`wget https://github.com/estuaryoss/estuary-agent-go/releases/download/4.2.1/estuary-agent-go`{{execute}}

Change the permissions  
`chmod +x estuary-agent-go`{{execute}}

Start the service  
`nohup ./estuary-agent-go &`{{execute}}

Check if the service has started  
`curl http://[[HOST_IP]]:8080/about`{{execute}}

