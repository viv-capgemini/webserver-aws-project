# webserver-aws-project
### This repo has been created to be used with terraform cloud to create infrastructure on AWS.

It will create an ec2 instance with a security group.
The security group provides http and ssh access to a paticular user. 

## Usage

See examples directory for working examples to reference:
```hcl
module "ec2_module" {
        source = "./modules/ec2/"
        env = "dev"
        vpc_security_group_ids = module.sg_module.aws_security_group_id
        instance_ami = "ami-0aaa5410833273cfe"
        instance_type = "t2.nano"
}

module "sg_module" {
        source = "./modules/security_group/"
        env="dev"
}
```