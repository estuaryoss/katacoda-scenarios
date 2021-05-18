Discovery CLI is an alternative to view the stack in real time similar with the Viewer:  
- the type of services currently registered in the same Eureka domain
- viewing active deployments
- viewing background command sessions

We will download the binary (platform specific)    
`wget -O discovery-cli https://github.com/estuaryoss/discovery-cli/releases/download/1.0.0/main-linux`{{execute}}

Change the permissions:
`chmod +x discovery-cli`{{execute}}

Let's create a configuration where we specify the Eureka server:
`echo eureka: \"http://[[HOST_IP]]:8080/eureka/v2\" > config.yaml`{{execute}}

Let's print the stack information:
`./discovery-cli --token=None --file="config.yaml" > output.txt`{{execute}}


For more info about the features and configuration, please visit [discovery-cli](https://github.com/estuaryoss/discovery-cli).

