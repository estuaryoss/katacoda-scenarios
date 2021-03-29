Now let's inspect the stack through the Discovery service:
- apps registered in Eureka
- deployments
- command sessions (background commands) from the agents

Let's list eureka apps:  
`curl http://[[HOST_IP]]:8081/eurekaapps | json_pp`{{execute}}  

Let's list deployments:  
`curl http://[[HOST_IP]]:8081/deployments | json_pp`{{execute}}  
There should be 2 deployments, one in each deployer service.

Let's list current test sessions:  
`curl -H 'Token:None' http://[[HOST_IP]]:8081/commandsdetached | json_pp`{{execute}}    
There should be 2 background command sessions, one on each agent service.

You can inspect the eureka apps through the Eureka registry:    
https://[[HOST_SUBDOMAIN]]-8080-[[KATACODA_HOST]].environments.katacoda.com/eureka  

You can also inspect the eureka apps through the Discovery:    
https://[[HOST_SUBDOMAIN]]-8081-[[KATACODA_HOST]].environments.katacoda.com/eurekaapps
