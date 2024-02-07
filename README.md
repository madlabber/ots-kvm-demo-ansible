# About this repository

This set of roles and playbooks demonstrates automating the following:
  - Preparing a KVM host
  - Installing the ONTAP Select Deploy VM
  - Creating an ONTAP Select cluster
  - Configuring an ONTAP Cluster

There are additional playbooks to demonstrate other operational tasks.

## Adjust variables to fit your environment

The end state variables are defined as inventory vars in YAML format in inventory/inventory.yml

Additional examples are in inventory/inventory-reference.yml

Example vault credentials are in the vars folder.

The inventory/inventory.yml file is set as the default inventory in ansible.cfg

## Install Ansible & NetApp Collections

```shell

ansible-galaxy install -r requirements.yml
```

## Prepare the KVM hosts

```shell
ansible-playbook playbooks/kvm_host_prep.yml
```
And individual host can be targeted with the limit (-l) parameter

```shell
ansible-playbook playbooks/kvm_host_prep.yml -l host01
```

## Install ONTAP Select Deploy

```shell
ansible-playbook playbooks/ots_deploy_install.yml 
```

## Create the ONTAP Select cluster

```shell
ansible-playbook playbooks/ots_cluster_create.yml 
```

To create only one cluster from the inventory, use the limit (-l) parameter:
```shell
ansible-playbook playbooks/ots_cluster_create.yml -l demo1
```

## Configure the ONTAP Select cluster

```shell
ansible-playbook playbooks/ots_cluster_configure.yml 
```
To configure only one cluster from the inventory, use the limit (-l) parameter:
```shell
ansible-playbook playbooks/ots_cluster_configure.yml -l demo1
```
