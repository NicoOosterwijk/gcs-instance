## About
This repostory provides the `gcloud` tool to manage google cloud platform.  


Virtual Machines
================
## Google Compute Engine
### Roles:
- create_instance
- stop_instance
- delete_instance

## How to use
You should setup your `gcloud` environment first, and you can refer to [here](https://cloud.google.com/compute/docs/gcloud-compute/#auth) to learn more about it.

## Setup the preferred group_vars, they are by default:
- Boot disk size: 10Gb
- OS: CentOS 7
- Zone: Europe West 4a
- Network tags: http-server,test-stretto-netw
- Nr. of instances to create: 4
- Name of instances: vm-nico-00x where x=the number of instances to create
- ssh key file: public key to use to logon - ~/.ssh/gcloud.pub

If you specify the ssh public key file, then gcloud will use that key when it create instances and you can connect to those instances without password
The format of key files should follow [Managing Instance Access with SSH Key Pairs](https://cloud.google.com/compute/docs/instances/adding-removing-ssh-keys)

Then, just run the create-instance playbook to create your virtual machines.
