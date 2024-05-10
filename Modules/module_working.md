# Module Command Execution and Working on AWS EC2 Linux Instance

This guide outlines the steps to create and execute a module command on an AWS EC2 Linux instance.

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

## 4. Ansible module command weare going to use are as follows:
- To install the httpd package we use command:

  `ansible domo -b -m yum -a "pkg=httpd state=present"`

  ![17](https://github.com/vivek2431/Ansible/assets/137812531/22925f48-08b9-491c-b63f-1d06c3de2149)

  ![18](https://github.com/vivek2431/Ansible/assets/137812531/3308fc4e-f2b1-43ef-b556-f16e623482a5)

-  Now we will check in our ansible server and in nodes that the file is created or not by using:

  ![19](https://github.com/vivek2431/Ansible/assets/137812531/4253032f-42d9-4a00-8a88-2104b8451a43)

  ![20](https://github.com/vivek2431/Ansible/assets/137812531/0014f267-948a-4fe0-8137-1dd30b935aaf)

- Check whether service httpd is active or not for that we use:

   `sudo service httpd status`

  ![25](https://github.com/vivek2431/Ansible/assets/137812531/adecefef-ca6b-4a78-a702-5ababc7cf4c8)

- if the `httpd`package is inactive then use this this command to activate package:

   `sudo service httpd start`

  ![27](https://github.com/vivek2431/Ansible/assets/137812531/87ca0dbb-3369-458c-b547-659a9a966ac0)

- To create an `user` in our demo group that we have created and check the staus:

   `ansible demo -b -m user -a "name=alex"`

  ![28](https://github.com/vivek2431/Ansible/assets/137812531/f1fd8028-73fe-4c96-a7cc-492d3d61ae42)

  ![29](https://github.com/vivek2431/Ansible/assets/137812531/36967f96-89ba-478b-a13d-d08751af519e)

  ![30](https://github.com/vivek2431/Ansible/assets/137812531/564a7d56-f29c-4839-b5e6-00bdc25fa08c)

- Now check in our nodes that the user is created bu using command:

  `cat /etc/passwd`

  ![31](https://github.com/vivek2431/Ansible/assets/137812531/b3790ed1-af17-4d72-9249-1a2f75a5e919)

  ![32](https://github.com/vivek2431/Ansible/assets/137812531/1e53cfb1-4556-4c8a-ab08-97bf8fa4e8b5)

  ![33](https://github.com/vivek2431/Ansible/assets/137812531/73a13265-0377-42f3-9edf-83cdccf31c93)

  ![34](https://github.com/vivek2431/Ansible/assets/137812531/dd3fbf2e-6c3b-4527-bbe1-0bbe83f0f498)

- To copy a file from our ansible server to our nodes we use a command:

   `ansible demo -b -m copy -a "src=randomfile dest=/tmp"`

  ![37](https://github.com/vivek2431/Ansible/assets/137812531/40c7a7c0-d29c-48ff-aabe-76ef02a9079a)

  ![38](https://github.com/vivek2431/Ansible/assets/137812531/447e700d-f9c2-4c41-9090-239d26b2d39a)

- To check in our nodes we use command"

   `ls /tmp/`

  ![39](https://github.com/vivek2431/Ansible/assets/137812531/44ba0dfd-8fc5-4d46-b0b1-0c7235bbf631)

  ![40](https://github.com/vivek2431/Ansible/assets/137812531/7359cb8d-97cd-47f9-a134-10a032e8c821)
 
- The `ansible` command with the `setup` module allows you to gather facts about the managed hosts in your inventory. These facts 
  include details about the host's hardware, operating system, network interfaces, and more.

  ![41](https://github.com/vivek2431/Ansible/assets/137812531/1fb18456-8e59-4408-9120-6964c54b565e)

  ![42](https://github.com/vivek2431/Ansible/assets/137812531/de9d4c87-299d-4731-92c8-ad73c9b263cb).

  ![43](https://github.com/vivek2431/Ansible/assets/137812531/08cc3d98-a46c-4540-b94c-77ff70e99c9f)


















 
    

