# Nuage VSD DB Restoration Automation 

This repo contains Ansible playbooks that restore a specified database backup at Nuage VSD standalone and cluster.

You can run the playbooks with the commands below

###### For Standalone:

```sh
ansible-playbook sa_vsd_restoration.yaml --extra-vars "backup_file=/tmp/backup/mydatabase-240229060529.tar.gz"
```
###### For Cluster:    
```sh
ansible-playbook cluster_vsd_restoration.yaml --extra-vars "backup_file=/tmp/backup/mydatabase-240301080020.tar.gz"
```

#### Prerequisites

##### Set the /etc/ansible/hosts


Set the ansible hosts file as below:
```
[vsd]
<sa vsd ip>

[vsd_cluster]
<cluster vsd1 ip>
<cluster vsd2 ip>
<cluster vsd3 ip>

[vsd_master]
<cluster master-vsd ip> // geenrally vsd1
```

##### Copy the public keys to the remote servers
```
ssh-copy-id root@<vsd ip>
```

