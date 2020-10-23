Now let's inspect the stack through estuary discovery:
- apps registered in Eureka
- deployments
- command sessions (background commands) from the agents

Let's list eureka apps:  
`curl http://[[HOST_IP]]:8081/eurekaapps | json_pp`{{execute}}  

Let's list deployments:  
`curl http://[[HOST_IP]]:8081/deployments | json_pp`{{execute}}  
There should be 2 deployments, one in each deployer service.

Let's list current test sessions:  
`curl http://[[HOST_IP]]:8081/commandsdetached | json_pp`{{execute}}    
There should be 2 background command sessions, one on each agent service.

And also you can inspect the eureka apps:    
https://[[HOST_SUBDOMAIN]]-8080-[[KATACODA_HOST]].environments.katacoda.com/eureka
