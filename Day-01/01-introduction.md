# Introduction to Ansible

## What is Ansible ?

Ansible is an open source IT automation engine that automates 
- provisioning 
- configuration management
- application deployment
- orchestration

and many other IT processes. It is free to use, and the project benefits from the experience and intelligence of its thousands of contributors.

## How Ansible works ?

Ansible is agentless in nature, which means you don't need install any software on the manage nodes.

For automating Linux and Windows, Ansible connects to managed nodes and pushes out small programs—called Ansible modules—to them. These programs are written to be resource models of the desired state of the system. Ansible then executes these modules (over SSH by default), and removes them when finished. These modules are designed to be idempotent when possible, so that they only make changes to a system when necessary.

For automating network devices and other IT appliances where modules cannot be executed, Ansible runs on the control node. Since Ansible is agentless, it can still communicate with devices without requiring an application or service to be installed on the managed node.

# Why is Ansible?

- Initially we used to have system admins there task is to setup configuration management.
- Suppose if they are working on a company where they have 5 physical servers, 4 linux with diff distributions and 1 windows. There tasks are
  1. Make sure centos distributon is upto date(not outdated) and supported version
  2. Make sure packages and libraries are upto date, suppose openssh, wget, curl, shared lib.
  3. Make sure App dependencies are latest, suppose for Java we need latest version, web servers and app servers are secure.
  4. Make sure CPU,memeory,RAM are available(maintainance).
- If they write shell scripts they might not work on windows only works on linux
- If, in linux OS, 2 are ubuntu and 2 are debaian it might fail. eg: for automating Java version, can write shell script using yum command, this might fail.
- To overcome this issues we need Ansible.
  
  ![image](https://github.com/Anusha2710/Ansible_anu/assets/47424821/be289437-1415-4d2d-8441-75256c6c773c)

# Ansible vs Puppet, Chef, Salt

- If we used to use Puppet, chef, salt tools we need to learn groovy,ruby and also we need to install packages in all target machines (Its not agentles)
  
 ![image](https://github.com/Anusha2710/Ansible_anu/assets/47424821/836700ef-fe39-4ff4-b5f7-bd4f1db0b2a5)

- Whereas in Ansible we need to know YAML and (no s/w installation on target machines (Agentless)
- We have Control Node(machine where ansible is installed) and Manage Node(machines where any package can install using control node)
  
![image](https://github.com/Anusha2710/Ansible_anu/assets/47424821/8e600f24-d548-45f0-872d-2ea620cfa8b7)

# What Ansible?

- Ansible can also do Provisioning, Configuring, Deploying, Network Automation
  
![image](https://github.com/Anusha2710/Ansible_anu/assets/47424821/68024977-7bd6-4f59-8a43-1989063fb3a3)

# Ansible vs Shell vs Python  

- If we got a task to install Java in 10 vms we can use Ansible, for python and shell we need programming learning.
- When to use python means - if we want to talk to APIs, create Jira ticket, GitHub issue through API
- For simple taks we can use shell
  
![image](https://github.com/Anusha2710/Ansible_anu/assets/47424821/578bdce3-41fc-4924-a7d9-539651a3c7e9)

# Ansible vs Terraform

- For configuration we can use Ansible and for IAC we use Terraform
- If org decides to purchase license from eg, redhat we can use Ansible to both IAC & Configuration management.

![image](https://github.com/Anusha2710/Ansible_anu/assets/47424821/0dbcac3f-d6d3-4a82-b7c1-59a63dd3ae9e)

- We need python installed for Ansible in Control and manage nodes, because Ansible takes YAML file and it converts it into python and executes python modules on manage nodes through ssh.

![image](https://github.com/Anusha2710/Ansible_anu/assets/47424821/b9176d79-3249-4be3-9499-9e1032666a1e)

![image](https://github.com/Anusha2710/Ansible_anu/assets/47424821/05e5f3c8-dfcb-4cfa-af70-eabd7b28e5b4)


![image](https://github.com/Anusha2710/Ansible_anu/assets/47424821/88bdbeb8-78e9-4262-8b27-840a688f8485)

- Through VSC or GtHub codespaces, we need YAML and Ansible extension
  



