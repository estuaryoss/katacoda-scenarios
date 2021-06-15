In this step we will see the commands executed at the beginning.

Let's download the CLI
`wget https://github.com/estuaryoss/seeder/releases/download/v1.0.0/seeder`{{execute}}

Let's give execute permission
`chmod +x seeder`{{execute}}

Let's issue a 'version --help'
`./seeder version --help`{{execute}}

Let's issue a 'version'  
`./seeder version`{{execute}}

Before moving to validate & init actions we must generate the global config.  
`echo -e "deploy_policy: fill #fill/robin \naccess_token: None \ndiscovery: \n  - \"http://[[HOST_IP]]:8081/\"" > config.yaml`{{execute}}

Let's issue a 'validate --help'  
`./seeder validate --help`{{execute}}

Let's issue a 'validate'  
`./seeder validate`{{execute}}

Let's issue a 'init --help'  
`./seeder init --help`{{execute}}

Let's issue a 'init'  
`./seeder init`{{execute}}
