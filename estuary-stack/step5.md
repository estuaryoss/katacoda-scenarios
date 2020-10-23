Now let's create a docker-compose template that will be used to start our first deployment.  

Let's open the docker-compose file and observe that the service will register to whatever Eureka server deployer knows. The template swap is done by the deployer using jinja2 templating.   
`docker-compose-discovery.yaml`{{open}}

Let's deploy the estuary discovery through the first estuary deployer, which will register to the Eureka server:   
`curl -X POST --data-binary @docker-compose-discovery.yaml -H "Content-type: text/x-yaml" http://[[HOST_IP]]:8083/docker/deployments`{{execute}}

Let's wait some time, until the deployment is up and running:  
`curl http://[[HOST_IP]]:8083/docker/deployments | json_pp`{{execute}}

Let's set the deployment ID in an env var to have it during this scenario:
`export DEPLOYMENT_DISCOVERY=$(curl http://[[HOST_IP]]:8083/docker/deployments | jq -r .description[0].id)`{{execute}}  

The deployment hash is:  
`echo $DEPLOYMENT_DISCOVERY`{{execute}}  

Let's connect this container to the deployer's net to be accessible. The deployment id can be obtained from any of the previous steps.  
`curl -X POST -i http://[[HOST_IP]]:8083/docker/deployments/network/$DEPLOYMENT_DISCOVERY`{{execute}}

Let's access the discovery through the deployer's net:  
`curl http://[[HOST_IP]]:8083/docker/container/$DEPLOYMENT_DISCOVERY/about | json_pp`{{execute}}

You can now see in the browser the new service registred in Eureka with the name having the deployment hash.  
This is the difference between a service registered directly to Eureka, and other registered through the deployer. 
https://[[HOST_SUBDOMAIN]]-8080-[[KATACODA_HOST]].environments.katacoda.com/eureka
