Let's supply a config where the commands are executed conditionally one-by-one on the server
`./main-cli --ip=localhost --port=8080 --token="" --file="config_remote_fail_on_first_err_server.yml" --interval=1 --batch=false`{{execute}}

The CLI halted the execution after first fail was detected on the server.  

You can edit the file 'config_remote_fail_on_first_err_server.yml' by removing 'invalid_command' and try again.
