<h1>Terraform Provisioning Project</h1>

<h2>Description</h2>
This project demonstrates how to use Terraform for AWS instance provisioning with automated configuration. It includes creating and managing SSH keys, launching EC2 instances, and configuring web servers using shell scripts. The project showcases various Terraform provisioners including file transfers and remote execution capabilities.
<br />


<h2>Languages and Utilities Used</h2>

<b>HashiCorp Configuration Language (HCL)
- Shell Scripting (Bash)
- YAML
- AWS CLI
<b>

<h2>Environments and tools Used </h2>

</b> AWS Account
- Terraform
- Git Bash or Linux Terminal
- AWS EC2
- SSH Key Pair Management</b>

<h2>Program walk-through:</h2>

<p align="center">
1. Setting Up the Project Structure
Create a new directory for the project and organize the following files:

  - providers.tf (AWS provider configuration)
- variables.tf (Variable definitions)
- instance.tf (Main infrastructure code)
- web.sh (Shell script for web server configuration)
<img src="https://res.cloudinary.com/dk3bkl3ji/image/upload/v1736900884/Screenshot_2025-01-14_192740_u8hsxe.png"/>
<br />
<br />

2. Generating SSH Key Pair
Generate a new SSH key pair using the ssh-keygen command:
ssh-keygen -f dove-key<br/>
This creates two files:

- key (private key)
- dove-key.pub (public key)
<img src="https://res.cloudinary.com/dk3bkl3ji/image/upload/v1737054874/Screenshot_2025-01-09_182922_yaimkl.png"/>
<br />
<br />

3. Creating the Variables File (variables.tf)
Set up the necessary variables for the project including:

- AWS region
- Availability zone
- AMI ID
- User credentials
<img src="https://res.cloudinary.com/dk3bkl3ji/image/upload/v1737055074/Screenshot_2025-01-16_141738_etxx0e.png"/>

<br />
<br />

4. Setting Up Provider Configuration (providers.tf)<br/>
Configure the AWS provider with the specified region from variables.
<img src="https://res.cloudinary.com/dk3bkl3ji/image/upload/v1737055247/Screenshot_2025-01-16_142033_l0sgbr.png"/>

<br />
<br />

5. Creating Web Server Configuration Script (web.sh)<br/>
Create a shell script to:

- Install Apache web server
- Configure basic settings
- Deploy sample web content
- Start and enable the service
<img src="https://res.cloudinary.com/dk3bkl3ji/image/upload/v1737055390/Screenshot_2025-01-15_134546_mvahop.png"/>

<br />
<br />

6. Main Infrastructure Configuration (instance.tf)
Create the main Terraform configuration to:

Upload SSH public key to AWS
Launch EC2 instance
Configure security groups
Set up provisioners for file transfer and remote execution
<img src="https://res.cloudinary.com/dk3bkl3ji/image/upload/v1737055618/Screenshot_2025-01-16_142633_o3ogtq.png"/>
<img src="https://res.cloudinary.com/dk3bkl3ji/image/upload/v1737055684/Screenshot_2025-01-16_142643_fkk4bi.png"/>
<img src="https://res.cloudinary.com/dk3bkl3ji/image/upload/v1737056020/Screenshot_2025-01-16_143328_lxyr7n.png"/>
<br />
<br />

7. Terraform Initialization and Validation<br/>
Initialize Terraform and validate the configuration:
- terraform init
- terraform validate
- terraform fmt
<br />
<br />

8. Deployment and Provisioning <br/>
Execute the Terraform plan and apply commands:
- terraform plan
- terraform apply
<br />
<br />



9. Verification <br/>
Verify the deployment:

- Check AWS Console for the EC2 instance
- Verify the key pair creation
- Test web server access
<img src="https://res.cloudinary.com/dk3bkl3ji/image/upload/v1737058851/Screenshot_2025-01-16_152034_nt4grr.png"/>
<br />
<br />

10. Cleanup
Remove all created resources:<br/>
- terraform destroy
