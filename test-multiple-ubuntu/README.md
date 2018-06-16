# test-multiple-ubuntu

This simple terraform script deploy multiple Ubuntu 16.04 virtual machine on VMware vSphere.

Count based on vsphere_ipv4_address variable.

Before use you must: 
 * symlink variable.tf from common folder of make own variable in current directory
 * rename vm.tf.example to your own vm.tfvars
 * init terraform by command "terraform init"
 * run terraform from current directory by command "terraform apply -var-file=../common/vsphere.tfvars -var-file=vm.tfvars -auto-approve"

Script created for test using on ansible.
