# AWS Load Balanced Web Application

## Project Overview
This project demonstrates deploying a highly available web application using AWS infrastructure. Multiple EC2 instances are placed behind an Application Load Balancer to distribute incoming traffic and improve reliability.

## Technologies Used
- AWS EC2
- Application Load Balancer (ALB)
- Target Groups
- Linux
- Nginx
- SSH

## Architecture
The application architecture consists of:
- Multiple EC2 instances running a web server
- An Application Load Balancer distributing traffic
- Target groups managing instance health checks
- Security groups controlling network access

## Deployment Steps
1. Launch EC2 instances
2. Connect to the instances using SSH
3. Install and configure Nginx
4. Start the web server service
5. Create an Application Load Balancer
6. Configure target groups
7. Register EC2 instances with the load balancer
8. Configure health checks to monitor instance availability

 ## 🧠 Architecture Decisions & Trade-Offs

### Compute Choice
I used EC2 instead of ECS.

- Pros:
  - Full control of the server
  - Easier for learning Linux

- Cons:
  - Always running → higher cost
  - Manual scaling

- Alternative:
  - ECS for container-based scaling

- Decision:
  EC2 was chosen for simplicity and learning purposes.  

## Key Commands Used
sudo systemctl start nginx
sudo systemctl status nginx
tail -f /var/log/nginx/error.log
curl localhost

## Troubleshooting
During deployment several issues were investigated including:
- Service status verification
- Log analysis
- Process checks
- Port verification
- AWS security group configuration

## What I Learned
- How to deploy scalable web applications on AWS
- How load balancers distribute traffic across instances
- How to troubleshoot Linux servers and web services
- How AWS networking and security groups affect connectivity

## 💸 Cost Optimization Considerations

- EC2 runs continuously, increasing cost
- Could switch to Lambda for low-traffic workloads
- Could implement auto-scaling to reduce idle usage
