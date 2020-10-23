Let's have an overview of the parallel mode.

Now let's execute multiple commands in sequential mode:
`curl -X POST -d $'sleep 1 && echo 1\nsleep 2 && echo 2' http://[[HOST_IP]]:8080/commandparallel | json_pp > parallel.json`{{execute}}

Open the **parallel.json** and observe the result for each command.  

In the parallel mode, the global duration is the max duration between all executed commands.  
Formula:  
```js
GLOBAL_DURATION = MAX(duration_cmd1, duration_cmd2, ...)
```


