Let's connect to this machine through REST API
`./main-cli --ip=[[HOST_IP]] --port=8080 --token=""`{{execute}}

Let's run a directory listing through the CLI
`ls -lrt`{{execute}}

Let's exit the cli  
`-trump`{{execute}}

Let's compare with local the system command 
`ls -lrt`{{execute}}

The output is the same, right?  

Keep in mind that the CLI is stateless, it does not keep the current working directory.   
It always defaults to the default directory from where the estuary-agent was previously started.  
