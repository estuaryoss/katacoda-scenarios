Now we will simulate a command session (multiple commands in background) on all three estuary agents.  
- the first which was deployed directly 
- the second which was deployed through the estuary deployer, and accessible through the deployer's net

Let's start a test session on the first agent:  
`curl -i --request POST http://[[HOST_IP]]:8082/commanddetached/101 --header 'Accept:application/json' --header 'Content-Type:text/plain' --data 'sleep 3 && echo test finished'`{{execute}}

Let's start the second test session on the second agent:  
`curl -i --request POST http://[[HOST_IP]]:8083/docker/container/$DEPLOYMENT_AGENT/commanddetached/102 --header 'Accept:application/json' --header 'Content-Type:text/plain' --data 'sleep 3 && echo test finished'`{{execute}}

Now let's list the active test sessions on both agents:  
`curl http://[[HOST_IP]]:8082/commanddetached | json_pp`{{execute}}
`curl http://[[HOST_IP]]:8083/docker/container/$DEPLOYMENT_AGENT/commanddetached | json_pp`{{execute}}
