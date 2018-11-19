## Tinkering with Ansible
This repository houses a series of example uses of Anisble

### Google Cloud (`/gce/`)
Build infrastructure on GCP Google Compute Engine using Ansible.

Requires GCE service account credentials or environment variables:
* See Ansible's [Google Cloud Platform Guide](https://docs.ansible.com/ansible/latest/scenario_guides/guide_gce.html#credentials)

###### `all-in-one.yaml`
This is a single file playbook, with included variables, for introductory testing.

* VPC Network, 1 subnet
* Firewall rule for SSH access
* VM instance with public IP and startup-script metadata

###### `modular.yaml`
This playbook utilizes `group_vars` variables and a common role with tasks.

* VPC Network, 1 subnet
* Firewall rule for SSH access
* VM instance with public IP and startup-script metadata


### Amazon Web Services (`/aws/`)
Build infrastructure on AWS using Ansible.

Requires AWS credentials via `~/.aws/credentials` file or environment variables:
* See Ansible's [Amazon Web Services Guide](https://docs.ansible.com/ansible/latest/scenario_guides/guide_aws.html#authentication)

###### `all-in-one.yaml`
This is a single file playbook, with included variables, for introductory testing.

* VPC
* Internet gateway
* 2 Subnets
* Routing table
* Security group for SSH access and open internal VPC communications
* EC2 instance with public IP and userdata script

###### `infra.yaml`
This playbook focuses on building just the VPC and network components

* VPC
* Internet gateway
* 4 Subnets (public)
* Route table
* Security group for SSH access and open internal VPC communications

###### `tower-lab.yaml`
This playbook (work-in-progress) is intended to provision an EC2 instance for deploying Ansible Tower.


### Microsoft Azure (`/azure/`)
Build infrastructure on Microsoft Azure using Ansible.

Requires Azure service principal credentials via `~/.azure/credentials` file or environment variables:
* See Ansible's [Microsoft Azure Guide](https://docs.ansible.com/ansible/latest/scenario_guides/guide_azure.html#authenticating-with-azure)

###### `infra.yaml`
This playbook focuses on building just the VPC and network components

* Resource group
* Virtual network
* Route table (no extra routes)
* 4 Subnets (public)
* Security group for SSH access
