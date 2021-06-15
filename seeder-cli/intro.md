This is seeder CLI, a powerful CLI inspired by Terraform and K8s.
The seeder CLI helps you to create multiple deployments for testing purposes, easy and simple.

The seeder talks:
- with a net of [Deployers](http://www.github.com/estuaryoss/estuary-deployer)
- with estuary stack formed from [Deployers](http://www.github.com/estuaryoss/estuary-deployer) and [Discovery(ies)](http://www.github.com/estuaryoss/estuary-discovery)

Before starting the scenario, please read the high-level description and the motivation [here](https://estuaryoss.github.io).
It should not take more than 10 minutes.  

In this scenario you will learn about:
- how to sync the local deployment plan with the remote state
- how to spread your deployments
- how to destroy your deployments at the end
- how to recreate your deployments

Before starting, you must have experience with:
- docker & docker-compose