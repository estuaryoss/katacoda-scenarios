Estuary viewer is a dashboard to view the stack in real time:  
- the type of services currently registered in the same Eureka domain
- viewing active deployments
- viewing background command sessions

Now we can deploy the Viewer and check the insights it offers. 
The stack can be in cloud or in K8s, or on your local domain, and be discoverable through Discovery.  
The Viewer communicates only with Discovery which aggregates all the information and send it back to the Viewer. 
It is a custom reverse proxy implementation, which uses multi-threading.  

Let's boot the Viewer. It has a larger RAM footprint, hope it will fit this Katacoda VM :)
`docker run -p 8084:8080 estuaryoss/viewer:latest bash -c "echo VUE_APP_ESTUARY_DISCOVERY=https://[[HOST_SUBDOMAIN]]-8081-[[KATACODA_HOST]].environments.katacoda.com > /home/node/app/.env; echo VUE_APP_HTTP_AUTH_TOKEN=None >> /home/node/app/.env;/home/node/app/start.sh"`{{execute}}

Let's see the dashboard:
https://[[HOST_SUBDOMAIN]]-8084-[[KATACODA_HOST]].environments.katacoda.com/

For more info about the features and configuration, please visit [estuary-viewer](https://github.com/estuaryoss/estuary-viewer).

