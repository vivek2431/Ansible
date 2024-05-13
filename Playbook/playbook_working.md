# Ansible Playbook Command Execution and Working on AWS EC2 Linux Instance

This guide outlines the steps to create and execute a ansible playbook command on an AWS EC2 Linux instance.

## 1. Setting Up AWS EC2 Instance

- Log in to your AWS Management Console.
- Launch an EC2 instance with a Linux operating system of your choice (e.g., Amazon Linux, Ubuntu, CentOS).
- Ensure that the instance has internet access and proper security group settings to allow connections.

   ![1](https://github.com/vivek2431/Ansible/assets/137812531/2e877889-78bb-4ace-a53a-4ccd7b315066)

## 2. Connecting to EC2 Instance

- Copy your `public ip` of your ansible server instance and paste it to putty.
- Use SSH to connect to your EC2 instance. You will need the key pair you created during the instance launch.
- ansible server (private ip): `172.31.28.219`
- Node1 (private ip): `172.31.18.184`
- Node2 (private ip): `172.31.18.86`

   Example:

   ![2](https://github.com/vivek2431/Ansible/assets/137812531/779d4e3b-083e-4a40-ab97-cf67a2fe050b)

   ![3](https://github.com/vivek2431/Ansible/assets/137812531/332b7d17-5b01-4797-b69f-b4abea2f76e4)

- Copy your Nodes public ip and login through putty.

  ![4](https://github.com/vivek2431/Ansible/assets/137812531/95c7ff11-d92f-41e5-90e2-e43e6e131d33)

## 3. Switch to ansible user that we have created earlier
- run `su - ansible` command in ansible server and in both the nodes we have created.

  ![5](https://github.com/vivek2431/Ansible/assets/137812531/a4a06f47-4947-41e2-b298-575b54103dc8)

## 4. Ansible Playbook command weare going to use are as follows:
- To see the list in our `demo` group that we have created is:

   `ansible demo -a "ls"`

   ![6](https://github.com/vivek2431/Ansible/assets/137812531/946487c6-4265-4393-ad4a-94229ded718a)

- To gather information about our nodes that are connected with our ansible server we use :
- Create a YAML file for your Ansible playbook, let's say playbook1.yaml and edit the file.

  `vi playbook1.yml`

   ![2](https://github.com/vivek2431/Ansible/assets/137812531/ea57819f-408b-4520-8c92-76f51c84292b)

- Define tasks to gather information about your nodes. For example, you can use Ansible's built-in modules like ec2_instance_info, setup, or shell to gather information such as instance details, system information, 
  or execute shell commands remotely. Edit the file and press `:wq` to save and exit

   ![3](https://github.com/vivek2431/Ansible/assets/137812531/6d29c220-2baa-4f50-ab17-2fc31345371a)

- Run the playbook using the ansible-playbook command.

   `ansible-playbook playbook1.yml`

   ![4](https://github.com/vivek2431/Ansible/assets/137812531/1adb7af8-d154-4f21-9f79-9b724418dbcc)

   After the execution of the run ansible playbook command we can see the `private ip` of our nodes.


