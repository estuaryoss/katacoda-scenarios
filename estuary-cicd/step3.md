Let's supply a config where some commands are executed remotely on the Agent.
`./main-cli --ip=localhost --port=8080 --token="" --file="config_remote.yml" --interval=1`{{execute}}

The batch of the commands are executed in this order:  
-  before_install
-  install
-  after_install
-  before_script
-  script
-  after_script

Now let's supply a config where a command fails on remote. The global execution status should be != 0.  
`./main-cli --ip=localhost --port=8080 --token="" --file="config_exit_1.yml" --interval=3`{{execute}}

Keep in mind that the CLI is stateless, it does not keep the current working directory.   
It always defaults to the default directory from where the estuary-agent was previously started.

! Because it's stateless, you must execute 'cd' commands if the path is outside the installation path of the Agent.   
E.g. 'cd your_dir && your_command'  
