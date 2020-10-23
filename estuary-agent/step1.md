Let's have an overview of the sequential mode.

Download the main service binary (platform-specific)    
`wget https://github.com/dinuta/estuary-agent/releases/download/4.0.8/main-linux`{{execute}}

Download the binary which permits running commands in the background (platform-specific)    
`wget -O start.py https://github.com/dinuta/estuary-agent/releases/download/4.0.8/start.py-linux`{{execute}}

Change the permissions for main service:   
`chmod +x main-linux`{{execute}}

Change the permissions for the start.py executable:   
`chmod +x start.py`{{execute}}

Start the service  
`nohup ./main-linux &`{{execute}}

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


