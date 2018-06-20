# terraform and ansible test, for local use

How to use:
* 0) Modify all .tf*.example files on ./terraform/common directory. Rename all .tf*.example .tf* files 
* 1) Create your VM by terraform ( Readme )
* 2) Add newly created VMS to .\ansible\inventories\templates\hosts 
* 3) Normalize VMs by playbook by command:
  * ansible-playbook -i \opt\ansible\inventories \opt\ansible\playbook\normalize_template.yml 


Temporally issues:
* 1) Right now is path-sensitive, must be in "/opt" directory. Some scripts works from any place, some won't
* 2) Newly-created terraforms VMs must be added on .\ansible\inventories\templates\hosts manually:
ubuntu ansible_ssh_host=192.168.100.2 

* 3) Because i have no DNS/DHCP server on test instance (hard way, i know) count of VMs based on number of ip in vmvars files. it was conceived before production use.




 
 
