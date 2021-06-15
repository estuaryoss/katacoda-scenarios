In this step we will see the commands executed at the beginning.

Let's download the CLI
`wget https://github.com/estuaryoss/estuary-agent-go/releases/download/v1.0.0/seeder`{{execute}}

Let's give execute permission
`chmod +X seeder`{{execute}}

Let's issue a 'version --help'
`seeder version --help`{{execute}}

Let's issue a 'version'
`seeder version`{{execute}}

Before moving to validate & init actions we must generate the global config.
`echo -e "deploy_policy: fill #fill/robin \n access_token: None \n discovery: \n  - \"http://[[HOST_IP]]:8081/\"" > config.yaml`{{execute}}

Let's issue a 'validate --help'
`seeder validate --help`{{execute}}

Let's issue a 'validate'
`seeder validate`{{execute}}

Let's issue a 'init --help'
`seeder init --help`{{execute}}

Let's issue a 'init'
`seeder init`{{execute}}

You can also see in the browser the services registered in Eureka.   
https://[[HOST_SUBDOMAIN]]-8080-[[KATACODA_HOST]].environments.katacoda.com/eureka
