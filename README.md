## Tinkering with Ansible
This repository houses a series of example uses of Anisble

### Google Cloud (`gce`)
Build infrastructure on GCP Google Compute Engine using Ansible.

###### `all-in-one.yaml`
This is a single file playbook, with included variables, for introductory testing.

* Requires GCE credentials via environment variables:
    * `GCE_EMAIL`
    * `GCE_PROJECT`
    * `GCE_CREDENTIALS_FILE_PATH`
* VPC Network, 1 subnet
* Firewall rule for SSH access
* VM instance with public IP and startup-script metadata

###### `modular.yaml`
This playbook utilizes `group_vars` variables and a common role with tasks.

* Requires GCE credentials via environment variables:
    * `GCE_EMAIL`
    * `GCE_PROJECT`
    * `GCE_CREDENTIALS_FILE_PATH`
* VPC Network, 1 subnet
* Firewall rule for SSH access
* VM instance with public IP and startup-script metadata


### Amazon Web Services (`aws`)
Build infrastructure on AWS using Ansible.

###### `all-in-one.yaml`
* Requires AWS credentials via environment variables:
    * `AWS_ACCESS_KEY_ID`
    * `AWS_SECRET_ACCESS_KEY`
* VPC
* Internet gateway
* 2 Subnets
* Routing table
* Security group for SSH access and open internal VPC communications
* EC2 instance with public IP and userdata script
