In this step, we will generate a more complex template with more than one environment variable and a more complex variable file.  

`docker run --rm -v $PWD/inputs/templates:/templates -v $PWD/inputs/variables:/variables -e DATABASE=mysql56 -e IMAGE=latest dinutac/jinja2docker:2.1.6 /templates/standalone.j2 /variables/variables.yml --format=yaml`{{execute}}


As stated in the previous step, an overview of the template and variable files can be seen in the root of the GitHub project [here](https://github.com/dinuta/jinja2docker) in the folder called **inputs**.
