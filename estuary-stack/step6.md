Let's deploy the agent through the second estuary deployer, which will register to the Eureka server:  
`curl -X POST --data-binary @docker-compose-agent.yaml -H "Content-type: text/x-yaml" http://[[HOST_IP]]:8083/docker/deployments`{{execute}}

Let's wait some time, until the deployment is up and running:  
`curl http://[[HOST_IP]]:8083/docker/deployments | json_pp`{{execute}}

Let's set the deployment ID in an env var to have it during this scenario:
`export DEPLOYMENT_AGENT=$(curl http://[[HOST_IP]]:8083/docker/deployments | jq -r .description[0].id)`{{execute}}  

The deployment hash is:  
`echo $DEPLOYMENT_AGENT`{{execute}}  

Let's connect this container to the deployer's net to be accessible. 
`curl -X POST -i http://[[HOST_IP]]:8083/docker/deployments/network/$DEPLOYMENT_AGENT`{{execute}}

Let's access the agent through the deployer's net:  
`curl -H Token:None http://[[HOST_IP]]:8083/docker/container/$DEPLOYMENT_AGENT/about | json_pp`{{execute}}

You can now see in the browser the new service registered in Eureka with the name having the deployment hash.   
https://[[HOST_SUBDOMAIN]]-8080-[[KATACODA_HOST]].environments.katacoda.com/eureka
