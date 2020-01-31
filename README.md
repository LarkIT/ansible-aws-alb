# Lark IT Ansible AWS ALB role
Creates an application load balancer, target group, security group, and a CNAME record in route 53 pointed at the ALB. 

## Dependencies
- Assumes SSL is not enabled on the target webserver
- Assumes that the target server is listening on port 80
- Assumes an AWS certificate exists
- This role is not dependent on any other roles

## Variables
| Variable | Required? | Default Value | Type | Description |
|----------|-----------|---------------|------|-------------|
| tg_health_check_path | No | / | String | Target group healthcheck path |
| alb_name | Yes | N/A | String | The name of the ALB |
| alb_target_ec2_name | Yes | N/A | String | The Name tag value of the target EC2 |
| alb_subnet_names | Yes | N/A | List | List of subnets for the ALB |
| alb_cert_arn | Yes | N/A | String | ARN of the certificate to attach to the ALB |
| r53_hosted_zone_name | Yes | N/A | String | The name of the hosted zone where the CNAME record will be placed |
| r53_record | Yes | N/A | String | Then name of the CNAME record to be created |
| r53_overwrite | No | false | Boolean | Whether or not to overwrite the CNAME record if it already exists |
