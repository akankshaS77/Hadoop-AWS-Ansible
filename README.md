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

To know more about it and To download Hadoop [Visit!](https://hadoop.apache.org/)

## Multi-Node Cluster

<h1 align=center>
  < img src="https://github.com/akankshaS77/Hadoop-AWS-Ansible/blob/main/MNA.gif" />
</h1>

### Used Ansible Roles for Configuring Hadoop Cluster:

* **`/hadoop-ws/role` folder**
  * **`./ec2` role** - To Launch instance using Ansible Automation and fetching IP dynamically into inventory
  * **`./hadoop_master` role** - To Configure hadoop Name node ( master ) using Ansible Automation
  * **`./hadoop_slave` role** - To configure hadoop Data Nodes ( slave ) using Ansible Automation
  * **`./hadoop_client` role** - To configure hadoop Client and attach with the Hadoop Multi-Node cluster

## How to run these roles ?

You Don't need to write 10+ commands on your CLI, Kidding :)

#### First Note the Pre-requisite to run this Role for Ease in Hadoop Multi-Node CLuster Setup:
* Ansible must be installed to your System. Mostly supported by Linux as Ansible is RedHat Product. (Prefer Ansible Version: 2.3.*)
  * Could be installed using Python
    `yum install python3`
    `pip3 install ansible`
  * Could be installed using yum repository RHEL
    `yum install ansible`

To know more about Ansible and Dowload Ansible [Visit!](https://www.ansible.com/)

#### Second Step is to download the code from github in one of the directory over the your Ansible Controller Node.
* Create a directory:
  `mkdir my-ws`
* Initialize as Git Repository
  `git init`
* Pull the code
  `git pull` [git url](https://github.com/akankshaS77/Hadoop-AWS-Ansible)

#### Just Put two files and make changes in two places.
* First Ansible Vault file named `cred.yml` which contain IAM access and Secret Key for Authentication to your AWS Account.
  In your directory 'my-ws' create using `ansible-vault create cred.yml` (give password)
  _file format:_
  access_key: GUJGWDUYGUEWVVFEWGVFUYV
  secret_key: huadub7635897^%&hdfqt57gvhg
* Second file named `hadoop_instance.pem` which is key-pair that we use to create the ec2-instance remotely over our AWS account.
  _Steps:_
  * Go to AWS Management Console 
  * EC2 dashboard
  * Key-pairs
  * Craete new Key-Pair
  * Give name as `hadoop_instance`
  * Select '.PEM' file format
  * Download the key to your local system
  * Transfer the key to Ansible Controller node in same directory where your role is `my-ws`

## Environment Ready to Setup Hadoop MNA!!

### Now, Just in one click you be able to setup whole Cluster over your AWS Account.
- Run this command inside your Directory `ansible-playbook setup.yml --ask-vault-pass` (Press Enter and Enter the vault password that you have given while creating cred.yml vault file).

### Check if Hadoop Setup and DataNodes connected to master by connecting ansible_master instance on the AWS EC2 dashboard 
- `hadoop dfsadmin -report`
- `jps`

## 🤩✨ Congratulations, Your Big-data Hadoop Multi-Node Cluster is Setup. :)

* Note: For any query related to this Project Connect us:
  * @raktim00 and @akankshaS77






