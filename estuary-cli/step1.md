To be able to control the machine over REST API you must deploy the agent.

Download the binary (platform specific)    
`wget https://github.com/dinuta/estuary-agent/releases/download/4.0.8/main-linux`{{execute}}

Change the permissions  
`chmod +x main-linux`{{execute}}

Start the service  
`nohup ./main-linux &`{{execute}}

Check if the service has started  
`curl http://[[HOST_IP]]:8080/ping`{{execute}}

