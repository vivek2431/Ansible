# Ad-hoc Commands in Ansible

Ad-hoc commands in Ansible are used for quick tasks or troubleshooting without the need for a playbook. They provide a way to execute simple tasks across one or multiple hosts directly from the command line using the `ansible` command with various options. Below is a breakdown of how to use ad-hoc commands:

## Basic Syntax:

```bash
ansible <pattern> -m <module> -a "<arguments>"
```
- `<pattern>`: Specifies the target hosts or groups. This can be a single host, a group of hosts, or a wildcard pattern.
- `<module>`: Specifies the Ansible module to execute on the target hosts.
- `<arguments>`: Additional arguments specific to the module being used.

### Example:
 1. Ping all hosts:

    `ansible all -m ping`
    
    This command sends a ping to all hosts to check if they are reachable.

2. Check disk space:

    `ansible webservers -m shell -a "df -h"`

     This command runs the df -h command on hosts in the "webservers" group to check disk space.

3. Copy a file:

   `ansible webservers -m copy -a "src=/path/to/local/file dest=/path/on/remote/file"`

   This command copies a file from the local machine to hosts in the "webservers" group

4. Install a package:

   `ansible db_servers -m yum -a "name=httpd state=latest"`

   This command installs the latest version of the httpd package on hosts in the "db_servers" group using `yum`.

5. Execute a shell command:

   `ansible database -m command -a "echo 'Hello, world!'"`

   This command runs the `echo 'Hello, world!'` command on hosts in the `"database"` group.

Ad-hoc commands are useful for tasks that don't require complex orchestration and are a quick way to perform common operations across multiple hosts. 
However, for more complex tasks or those requiring state management, writing playbooks is recommended.




