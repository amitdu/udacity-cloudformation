## Live URL for Load Balancer

`http://serve-webap-1dh15gga2cgzm-2050747410.us-east-2.elb.amazonaws.com`

## Project Overview

Infrastructure as Code
In this project, I have deployed web servers for a highly available web app using CloudFormation.
I have written the code that creates and deploys the infrastructure and application for an Instagram-like app from the ground up. I have deployed the networking components, followed by servers, security roles and software.

### Project Structure

- `docs` : Documents related to Infra
- `infra` : Infrastructure as Code
- `infra > network` : Network related components
- `infra > server` : Server related components
- `infra > scripts` : Bash script for running cloudformation

## Setup the Environment

- Need to configure aws env `aws configure`

### Scripts

- Go to `scripts` dir `cd infra/scripts` and `chmod +x *` to add execute permission
- Create networking components first as they are dependency for server components

* `./create-stack.sh <network_stack_name> ../network/network.cf.yml ../network/network.param.json` : creates the network stack
* `./create-stack.sh <server_stack_name> ../server/server.cf.yml ../server/server.param.json` : : creates the server stack
* `./delete-stack.sh <stack_name>` : Deletes the <stack_name>
* `./update-stack.sh <server_stack_name> <cf_config_file> <parameters_file>` : Update the stack
