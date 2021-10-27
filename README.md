# Deploy Docker Image on AWS ECS Task and Service via Ansible
Ansible code to deploy Docker image on ECS

**Pre-requisites:**
- EC2 instance(test account) with Ansible installed 
    
    Commands:
        
		- yum install pip
        
		- pip install ansible
        
		- pip install boto
        
		- pip install botocore

- Create an EC2 key_pair in AWS and pass it as a parameter to ansible-playbook

**Process:**
- vpc_create : 
     * It creates the VPC, subnets, Internet Gateway, Routing Table and Security groups.
- ecs_cluster :
     * It creates ECS cluster, IAM linked role, load balancer, Target group, ECS task deinition and ECS Service.

**How to Deploy:**
- Run the below command to Deploy your docker container to ECS using ansible
       ansible-playbook ansible-ecs-deploy-playbook.yml --extra-vars "aws_keypair= $keypair_value"
- Test the application using the load balancer URL.
