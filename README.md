## About
This repostory provides the `gcloud` tool to manage google cloud platform.  

Virtual Machines
================
## Google Compute Engine
### Roles:
- create_instance
- stop_instance
- delete_instance
- create_group

## How to use
You should setup your `gcloud` environment first, and you can refer to [here](https://cloud.google.com/compute/docs/gcloud-compute/#auth) to learn more about it.

The next step will be to create and add your **ssh-key** to the Google Compute Engine metadata. Use the [Google Cloud Console](https://console.cloud.google.com) to add your key.

## Setup the preferred group_vars, they are by default:
- Boot disk size: **10Gb**
- OS: **CentOS 7**
- Machine-type: **n1-standard-1** (1 CPU, 4Gb memory)
- Zone: **Europe West 4a**
- Network tags: **http-server,test-nico-netw**
- Nr. of instances to create: **4**
- Name of instances: **tst-nico-00x** (where x=the number of instances to create)
- ssh key file: **~/.ssh/gcloud.pub**

If you specify the ssh public key file, then gcloud will use that key when it create instances and you can connect to those instances without password
The format of key files should follow [Managing Instance Access with SSH Key Pairs](https://cloud.google.com/compute/docs/instances/adding-removing-ssh-keys)

# Playbooks:

## Create_Instances
Then, just run the create-instance playbook to create your virtual machines:
**ansible-playbook create_instance.yaml**

## Create_groups
### This role will create the admin and db instance groups and add the instances to it.
instance 1 and instance 2 will be members of the admin-group,
instance 3 and instance 4 will be members of the db-group.

# Execute:
Run the following command to create instances and place them into groups:
```sh
$ ansible-playbook site.yml
```


