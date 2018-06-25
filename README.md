# terraform and ansible test, for local use

How to use:
* 0) Modify all .tf*.example files on ./terraform/common directory. Rename all .tf*.example .tf* files 
* 1) Create your VM by terraform ( Readme )
* 2) Add newly created VMS to .\ansible\inventories\templates\hosts 
* 3) Normalize VMs by playbook by command:
  * ansible-playbook -i \opt\ansible\inventories \opt\ansible\playbook\normalize_template.yml 


Temporally issues:
* 1) ~~Right now is path-sensitive, must be in "/opt" directory. Some scripts works from any place, some won't~~
* 2) Newly-created terraforms VMs must be added on .\ansible\inventories\templates\hosts manually:
ubuntu ansible_ssh_host=192.168.100.2 

* 3) Because i have no DNS/DHCP server on test instance (hard way, i know) count of VMs based on number of ip in vmvars files. it was conceived before production use.
```
├── ansible 
│   ├── inventories
│   │   ├── staging
│   │   │   ├── group_vars
│   │   │   │   └── all
│   │   │   ├── hosts
│   │   │   └── host_vars
│   │   └── templates
│   │       ├── group_vars
│   │       │   └── all
│   │       ├── hosts
│   │       └── host_vars
│   ├── playbook
│   │   ├── normalize_template.yml
│   ├── tasks
│   │   ├── hosts_stage.yml
│   │   ├── task_add_deploy_user.yml
│   │   ├── task_check_user.yml
│   │   └── task_move_to_stage.yml
│   └── templates
│       └── hosts.j2
└── terraform
    ├── common
    │   ├── variables.tf
    │   └── vsphere.tfvars
    ├── test-multiple-ubuntu
    │   ├── multiple-ubuntu.tf
    │   ├── README.md
    │   ├── variables.tf -> ../common/variables.tf
    │   └── vm.tfvars
    └── test-solo-ubuntu
        ├── README.md
        ├── solo-ubuntu.tf
        ├── variables.tf -> ../common/variables.tf
        └── vm.tfvars
```

 
 
