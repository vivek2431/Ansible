# Ad-Hoc Command Execution and Working on AWS EC2 Linux Instance

This guide outlines the steps to create and execute a Ad-hoc command on an AWS EC2 Linux instance.

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

## 4. Ansible Ah-hoc command weare going to use are as follows:
- To see the list in our `demo` group that we have created is:

   `ansible demo -a "ls"`

   ![6](https://github.com/vivek2431/Ansible/assets/137812531/946487c6-4265-4393-ad4a-94229ded718a)

- We will create one file by the name of 'opsfile` and that file will also be created in our nodes as well

   `ansible all -a "touch opsfile"`

   ![7](https://github.com/vivek2431/Ansible/assets/137812531/5d3e2eed-599a-4e87-b026-1180dee18a25)

- Now we will check in our nodes that the file is created or not by using:

   `ls`

   ![8](https://github.com/vivek2431/Ansible/assets/137812531/db993f50-728c-41b8-8414-03b55915365f)

   ![9](https://github.com/vivek2431/Ansible/assets/137812531/314f5f17-cd7f-4519-965c-9f1d1f021794)

- To see the all list that are present in our server:

  `ansible demo -a "ls -al"

  ![10](https://github.com/vivek2431/Ansible/assets/137812531/3a1559a5-9772-4977-9c53-056ca9b6f308)

- To install the httpd package in our ansible server and in our node we use:

   `ansible demo -a "sudo yum install httpd -y"`

  ![11](https://github.com/vivek2431/Ansible/assets/137812531/04f036b9-9f52-4627-bf2b-8e0d4f6c5d15)

  ![12](https://github.com/vivek2431/Ansible/assets/137812531/fd958d83-663a-4af6-be45-d3e80f813e56)

- To check whether httpd package is installed in our ansible server and in nodes run command:

   `which httpd`

  ![13](https://github.com/vivek2431/Ansible/assets/137812531/d1345f45-1f24-4aba-816c-bc711f754a75)

  ![14](https://github.com/vivek2431/Ansible/assets/137812531/66025b88-2184-431e-9ab1-1713118bb065)

-To remove or to delete the package we can use:

 `ansible demo -ba "yum remove httpd-y"`

 ![15](https://github.com/vivek2431/Ansible/assets/137812531/0300e85b-ad7c-48c3-90f5-4c0c1e6621f8)

 ![16](https://github.com/vivek2431/Ansible/assets/137812531/6ef8b297-a70e-413c-9e58-eea0a5b1b910)














