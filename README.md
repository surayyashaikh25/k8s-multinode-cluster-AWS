Role Name
=========

Kubernetes Multi Node Cluster On AWS.
This Role is to create Kubernetes Multi Node Cluster On AWS with 1 Master node & many worker nodes by default we have 2 nodes  but we can scale it. 


Requirements
------------

In the case, If you already have AWS EC2 instances created (master and worker instances but not configured) then you need to manually create the inventory 
  " ```
  <--
  [master]
  IP of master
  [worker]
  IPs of workers
  -->
  ``` " 
  _Meaning:_ we have 2 hostgroups one for Master and another for Worker nodes
  * But if you want to provision the ec2 instances automatically for K8s cluster using playbook then you can use the playbook that I have created [EC2 playbook](https://github.com/surayyashaikh25/kube-cluster-ansible/blob/master/ec2.yml "ec2.yml") 
  * You will need to specify your AWS Access Key & AWS Secret Key and also your public key in playbook. for access key and secret key you can make ansible vault file
Role Variables
--------------

This role doesn't require any variable to be specified by the user.
Dependencies
------------

This will work as it is without any dependency on other Galaxy roles. Because this role is stand alone.
Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:
" ```
<--
  - hosts: master
  gather_facts: no
  tasks:

          - name: Call the role
            include_role:
                    name: surayyashaikh25.k8s-multinode-cluster-AWS

- hosts: worker
  gather_facts: no
  tasks:
          - name: Call the role
            include_role:
                  name: surayyashaikh25.k8s-multinode-cluster-AWS
-->
  ``` "

License
-------

BSD

Author Information
------------------

This Role is created by Surayya Shaikh. For any queries, suggestions, corrections please contact here:[LinkedIn](linkedin.com/in/surayya-shaikh)
## k8s-multinode-cluster-AWS
