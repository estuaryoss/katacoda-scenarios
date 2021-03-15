To be able to run your small CI/CD flows over REST API you must deploy the Agent.

Download the binary (platform specific)    
`wget https://github.com/estuaryoss/estuary-agent-go/releases/download/4.2.0/estuary-agent-go`{{execute}}

Change the permissions  
`chmod +x estuary-agent-go`{{execute}}

Start the service  
`nohup ./estuary-agent-go &`{{execute}}

Download the binary which permits running commands in the background (platform-specific)    
`wget https://github.com/estuaryoss/runcmd/releases/download/1.0.0/runcmd-linux -O runcmd`{{execute}}

Change the permissions for the start.py executable:   
`chmod +x runcmd`{{execute}}

Check if the service has started  
`curl http://[[HOST_IP]]:8080/about`{{execute}}

