The deployer orchestrates your deployments via REST API.  
It deploys your dev/test environment using docker-compose templates on docker, or it acts as proxy in front of k8s cluster using kubectl.

More info about how it works you can find by visiting [wiki](https://github.com/estuaryoss/estuary-deployer/wiki).

Estuary deployer manages the deployments:
 - create deployment
 - delete deployments
 - list deployments
 - interact with containers/services inside deployments

The deployer supports the deployment of agents and discovery(ies) with k8s/docker-compose templates.
In docker, a specific service/container can be accessed by connecting the service to the deployer's network.

The first required step is to create a network for the deployer, which will be used to further access the targeted containers/services in a deployment.  
`docker network create estuarydeployer`{{execute}}

Let's start the first deployer service and instruct it to connect to the Eureka registry:  
`docker run -d -e HTTP_AUTH_TOKEN=None -e EUREKA_SERVER=http://[[HOST_IP]]:8080/eureka/v2 -e APP_IP_PORT=[[HOST_IP]]:8083 -p 8083:8080 -v /var/run/docker.sock:/var/run/docker.sock --net=estuarydeployer estuaryoss/deployer:4.2.3`{{execute}}

Let's verify that the Deployer started:  
`curl -H Token:None http://[[HOST_IP]]:8083/docker/about | json_pp`{{execute}} 

Let's list again the eureka apps, and see the new service registered:  
`curl http://[[HOST_IP]]:8081/eurekaapps | json_pp`{{execute}}

You can now see in the browser the new service registred in Eureka.   
https://[[HOST_SUBDOMAIN]]-8080-[[KATACODA_HOST]].environments.katacoda.com/eureka

For more info about the features and configuration, please visit [estuary deployer](https://github.com/estuaryoss/estuary-deployer).
