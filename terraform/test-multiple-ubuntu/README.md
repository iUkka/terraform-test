# test-multiple-ubuntu

This simple terraform script deploy multiple Ubuntu 16.04 virtual machine on VMware vSphere.

Count based on vsphere_ipv4_address variable.

Before use you must: 
 * rename ..\common\vsphere.tfvars.example to ..\common\vsphere.tfvars and modify it to your own
 * modify and symlink variable.tf from ..\common of make own variable in current directory
 * rename terraform.tfvars.example to your own terraform.tfvars (and put ../common/vsphere.tfvars variables to your terraform.tfvars if you dont want have extra -var-file=../common/vsphere.tfvars on command line)
 * init terraform by command "terraform init"
 * plan your config by terraform plan:
   * 1a. copy/add variables from  ./common/vsphere.tfvars.example to your terraform.tfvars and run terraform from current directory by command "terraform plan"
     or
   * 1b. run terraform from current directory by command "terraform apply -var-file=../common/vsphere.tfvars -var-file=terraform.tfvars 
 * run terraform apply from current directory by command 
   * 1a. "terraform apply" 
     or 
   * 1b "terraform apply -var-file=../common/vsphere.tfvars -var-file=vm.tfvars -auto-approve"
 * destroy VMs by command "terraform destroy -var-file=../common/vsphere.tfvars -var-file=terraform.tfvars -force"