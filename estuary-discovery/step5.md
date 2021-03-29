Now we will simulate a command session (multiple background commands) on all three estuary agents.

Let's start a command session through the discovery, which will trigger a unicast message to all agents: 
`curl -i -X POST http://[[HOST_IP]]:8081/agents/commanddetached/1 --header 'Accept:application/json' -H 'Content-Type:text/plain' -H 'IpAddr-Port:[[HOST_IP]]:8082' --data $'sleep 1 \n echo test finished'`{{execute}}

`curl -i -X POST http://[[HOST_IP]]:8081/agents/commanddetached/2 --header 'Accept:application/json' -H 'Content-Type:text/plain' -H 'IpAddr-Port:[[HOST_IP]]:8083' --data $'sleep 2 \n echo test finished'`{{execute}}

`curl -i -X POST http://[[HOST_IP]]:8081/agents/commanddetached/3 --header 'Accept:application/json' -H 'Content-Type:text/plain' -H 'IpAddr-Port:[[HOST_IP]]:8084' --data $'sleep 3 \n echo test finished'`{{execute}}

Now let's list the active command sessions on both agents:  
`curl http://[[HOST_IP]]:8082/commanddetached | json_pp > agent1.json`{{execute}}

`curl http://[[HOST_IP]]:8083/commanddetached | json_pp > agent2.json`{{execute}}

`curl http://[[HOST_IP]]:8084/commanddetached | json_pp > agent3.json`{{execute}}

We can do the same thing through the Discovery service:  
`curl http://[[HOST_IP]]:8081/commandsdetached | json_pp > discovery_all_agents.json`{{execute}}

The broadcast command propagated to all agents. All agents have now different command session IDs: **1,2,3**;
