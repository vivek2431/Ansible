
# Ansible Playbooks

Ansible playbooks are structured documents written in YAML format that define sets of tasks to be executed on remote hosts. They serve as the core of Ansible's configuration management system, automating tasks such as provisioning servers, configuring software, deploying applications, and orchestrating complex workflows.

## Components of a Playbook

### Hosts

Specifies the target hosts or groups of hosts where the tasks will be executed.

### Variables

Defines variables that customize behavior based on different environments or conditions.

### Tasks

Contains a list of tasks to be executed sequentially on the target hosts. Each task typically involves invoking Ansible modules to perform specific actions such as installing packages, copying files, managing services, and executing commands.

### Handlers

Defines handlers, which are tasks triggered only if other tasks in the playbook make changes to the system. Handlers are useful for tasks like restarting services after configuration changes.

### Roles

Organizes tasks, variables, and other files into reusable units called roles, allowing for better modularity and code organization.

## Example Ansible Playbook

This is a simple example of an Ansible playbook that installs and configures Apache on remote servers.

## Usage

1. Make sure you have Ansible installed on your local machine.
2. Create a file named `example.yml` and paste the following content into it:

```yaml
---
- name: Example Playbook
  hosts: web_servers
  become: true
  tasks:
    - name: Ensure Apache is installed
      package:
        name: apache2
        state: present

    - name: Ensure Apache is running
      service:
        name: apache2
        state: started
        enabled: true
```
- Replace `web_servers` with the appropriate hostname or group of hosts in your inventory.
- Execute the playbook using the following command:

  `ansible-playbook example.yml`

This command will execute the tasks defined in the playbook on the specified hosts.

## Explanation

- `name`: Provides a descriptive name for the playbook.
- `hosts`: Specifies the target hosts or groups of hosts where the tasks will be executed.
- `become`: true: Indicates that the tasks should be executed with elevated privileges (usually using sudo).
- `tasks`: Contains a list of tasks to be executed, each with a name and a module (e.g., package, service) along with parameters specific to that module.
