## About
This repostory provides the `gcloud` tool to manage google cloud platform.  


Virtual Machines
================
##Google Compute Engine
### Create instances
#### boot_disk_size
#### boot_disk_type
#### instance_name
#### image_family
#### image_project
#### can_ip_forward
#### zone
#### ssh-key-file
#### tags
If you specific the ssh public key file, the gcloud will use those key when it create instances and you can connect to those instances without password
The format of key files should follow [Managing Instance Access with SSH Key Pairs](https://cloud.google.com/compute/docs/instances/adding-removing-ssh-keys)

## How to use
You should setup `gcloud` environment first, and you can refer to [here](https://cloud.google.com/compute/docs/gcloud-compute/#auth) to learn more about it.

##Setup your preferred group_vars, they are by default:
- Boot disk size: 10Gb
- OS: CentOS 7
- Zone: Europe West 4a
- Network tags: http-server,test-stretto-netw
- Nr. of instances to create: 4
- Name of instances: tst-stretto-00x where x=the number of instances to create

Then, just run the create-instance playbook 
