Let's have an overview of the background mode.

Now let's execute multiple commands in sequential mode:
`curl -X POST -d $'sleep 1 && echo 1\nsleep 2 && echo 2' http://[[HOST_IP]]:8080/commanddetached/myCommandID | json_pp > background_post.json`{{execute}}

Observe that the API is returning a response immediately having the description your previously set command ID.   

Now let's inspect the result of the commands executed in background for the command ID previously set:
`curl http://[[HOST_IP]]:8080/commanddetached | json_pp > background_get.json`{{execute}}

You can try with higher sleeps and more commands, to observe the status of the commands live:
- in progress
- scheduled
- finished

Open the **background_get.json** / **background_post.json** and observe the result for each command.  
In the detached mode, the global duration is also the sum of duration of each command. 
Formula:  
```js
GLOBAL_DURATION = SUM(duration_cmd1, duration_cmd2, ...)
```


