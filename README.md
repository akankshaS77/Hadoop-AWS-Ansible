# Hadoop-AWS-Ansible
Hadoop multi-node cluster setup on AWS EC2 instances using Ansible.


### Configure Hadoop and start cluster services using Ansible Playbook over AWS
1. Configure Name Node using Ansible.
2. Configure Data Node using Ansible.
3. Start HDFS Service. 
4. Connect to Client.

## Technologies Used:
- Big Data
- DevOps
- Cloud Computing

### 🤔 Pondering what hadoop is?
Hadoop is an Apache Framework to Do Big Data Computing and Storage through Distributed Approach. Big Size files are Stripped out in some block sizes and Stores at different Data Storage Nodes using HDFS protocol. Benefit of the tool is that I/O process become faster. Data is relable as internally it replicated in containers and also uaing Map Reduce Concept we can do Analysis and Processing of Data easily.

To know more about it and To download Hadoop (Visit!)[https://hadoop.apache.org/]

![**Multi-node CLuster**](https://github.com/akankshaS77/Hadoop-AWS-Ansible/blob/main/MNA.gif)

### Used Ansible Roles for Configuring Hadoop Cluster:

* **`/hadoop-ws/role` folder**
  * **`./ec2` role** - To Launch instance using Ansible Automation and fetching IP dynamically into inventory
  * **`./hadoop_master` role** - To Configure hadoop Name node ( master ) using Ansible Automation
  * **`./hadoop_slave` role** - To configure hadoop Data Nodes ( slave ) using Ansible Automation
  * **`./hadoop_client` role** - To configure hadoop Client and attach with the Hadoop Multi-Node cluster

### How to run these roles ?

You Don't need to write 10+ commands on your CLI, Kidding :)

#### First Note the Pre-requisite to run this Role for Ease in Hadoop Multi-Node CLuster Setup:



