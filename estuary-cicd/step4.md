Let's supply a config where we upload and download files on/from the remote Agent.
The Agent is on this machine we'll demonstrate this feature by using different paths.  

`./main-cli --ip=localhost --port=8080 --token="" --file="config_files_upload_download.yml" --interval=3`{{execute}}

In background the following steps happened: 
-  The cli uploaded the cicd flow cicd_flow.sh. It can be any script in any language. (Python, Ruby, etc)  
-  The Agent ran this flow
-  The Agent streamed back the output/error back to you

In the flow a file download was executed also. You can the file downloaded from the agent:    
`cat os-release.txt`{{execute}}
