Download the CLI (binary & platform specific)  
`wget -O main-cli https://github.com/estuaryoss/agent-cli/releases/download/4.1.1/main-linux`{{execute}}

Change the permissions  
`chmod +x main-cli`{{execute}}

Let's list the current working directory  
`./main-cli --ip=[[HOST_IP]] --port=8080 --token="" --cmds="ls -lrt;;-trump"`{{execute}}

Let's do the same with the system command  
`ls -lrt`{{execute}}

The output is the same, right?  
