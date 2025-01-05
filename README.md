# packer-custom-ami
# Packer AMI AWS

This repository demonstrates how to create an AWS AMI using HashiCorp Packer. The configuration uses the `amazon-ebs` builder to provision and customize the AMI.

## Prerequisites

Before you begin, ensure the following prerequisites are met:

1. **Packer Installation**  
   Download the [Packer binary](https://www.packer.io/downloads) and place it in the desired folder.

2. **AWS Configuration**  
   - Ensure the subnets are set to **auto-assign public IPs**.
   - Configure the **Security Group (SG)** to allow SSH access.
   - Place the instance in a **public subnet** with proper routing in the route table (RT).

3. **Packer Plugins**  
   Install the `amazon-ebs` Packer plugin using the following command:
   ```bash
   packer init .

File Structure
packer.json: The main Packer configuration file for building the AMI.
packer-vars.json: A variable file containing custom values used in the configuration.
Usage
Validate Configuration
Validate the Packer configuration to ensure it is syntactically correct.

bash
Copy code
packer.exe validate --var-file=packer-vars.json packer.json
Inspect Configuration
Inspect the Packer template to see details of the build process.

bash
Copy code
packer.exe inspect --var-file=packer-vars.json packer.json
Build AMI
Build the AMI using the Packer template and variables file.

bash
Copy code
packer.exe build --var-file=packer-vars.json packer.json
Notes
Ensure that the Packer configuration references the correct AWS credentials for accessing the target account.
Always verify that the Security Group rules and subnet configurations are suitable for your requirements.
Check the packer-vars.json file to ensure it contains all necessary values (e.g., AWS region, instance type, etc.).
Troubleshooting
Error: No SSH connection
Verify the instance is in a public subnet.
Ensure the Security Group allows inbound SSH traffic on port 22.
Error: Unable to route traffic
Check the route table associated with the public subnet to confirm it has a valid route to the internet gateway.

<img width="406" alt="image" src="https://github.com/user-attachments/assets/d81f9e6f-a123-485c-8738-8ca8632fbdc3" />

<img width="781" alt="image" src="https://github.com/user-attachments/assets/04fdf7da-0884-4d19-8fcf-d6eac0421e6c" />

