Let's have an overview of the sequential mode.

Download the main service binary (platform-specific)    
`wget https://github.com/estuaryoss/estuary-agent-go/releases/download/4.2.1/estuary-agent-go`{{execute}}

Download the binary which permits running commands in the background (platform-specific)    
`wget https://github.com/estuaryoss/runcmd/releases/download/1.0.0/runcmd-linux -O runcmd`{{execute}}

Change the permissions for main service:   
`chmod +x estuary-agent-go`{{execute}}

Change the permissions for the start.py executable:   
`chmod +x runcmd`{{execute}}

Start the service  
`nohup ./estuary-agent-go &`{{execute}}

Check if the service has started  
`curl http://[[HOST_IP]]:8080/ping`{{execute}}

Now let's execute multiple commands in sequential mode:
`curl -X POST -d $'sleep 1 && echo 1\nsleep 2 && echo 2' http://[[HOST_IP]]:8080/command | json_pp > sequential.json`{{execute}}

Open the **sequential.json** and observe the result for each command. 

There is a global *duration* and a local duration for each command.   
In the sequential mode, the global duration is the sum of the duration of each command.  
Formula:  
```js
GLOBAL_DURATION = SUM(duration_cmd1, duration_cmd2, ...)
```


