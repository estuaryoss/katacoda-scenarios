Download the CLI (binary & platform specific)  
`wget -O main-cli https://github.com/estuaryoss/estuary-cicd/releases/download/0.2.7/main-linux`{{execute}}

Change the permissions  
`chmod +x main-cli`{{execute}}

Let's supply a config where some commands are executed locally inside this CLI.
`./main-cli --ip=localhost --port=8080 --token="" --file="config_client.yml" --interval=2`{{execute}}

The batch of the commands are executed under the 'client_script' section inside the yaml file.  

The execution of the 'client_script' is conditional. It will exit at the first detected error.  
