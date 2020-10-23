In this step, we will generate a simple template with only one environment variable.  

Let's pull the docker image:  
`docker pull dinutac/jinja2docker:2.1.6`{{execute}}

Let's print the Jinja2 version inside the running container:  
`docker run --rm dinutac/jinja2docker:2.1.6 --version`{{execute}}

Now, let's download some templates & variables files:  
`git clone https://github.com/dinuta/jinja2docker.git`{{execute}}

Let's change the current working directory:  
`cd jinja2docker`{{execute}}

Let's obtain our very first generated template output:  
`docker run --rm -v $PWD/inputs/templates:/templates -v $PWD/inputs/variables:/variables dinutac/jinja2docker:2.1.6 /templates/json.j2 /variables/json.json --format=json`{{execute}}

An overview of the template and variable files can be seen in the root of the Github project [here](https://github.com/dinuta/jinja2docker) in the folder called **inputs**.
