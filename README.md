Debug Assignment CDO - Deployment Instructions

Prerequisites:
- Terraform
- Docker
- Ansible

Docker:
1. Build the Docker images:
   docker build --platform linux/amd64 -t salamaattia/tdf-mvc:0.0.1.RELEASE .
   docker push salamaattia/tdf-mvc:0.0.1.RELEASE
   docker build --platform linux/amd64 -t salamaattia/tdf-db:0.0.1.RELEASE .
   docker push salamaattia/tdf-db:0.0.1.RELEASE
2. Start the services:
   docker-compose up

Terraform:
1. cd terraform
2. terraform init
3. terraform apply

Ansible:
1. Update ansible_hosts with EC2 public IP.
2. Run ansible playbook:
   ansible-playbook -i ansible_hosts playbooks.yml

Deploy and Run the Application:
1. docker-compose up

Access the API:
- http://<EC2-PUBLIC-IP>:3000/tour-de-france/cyclists
- http://<EC2-PUBLIC-IP>:3000/tour-de-france/teams

Cleanup:
terraform destroy
 