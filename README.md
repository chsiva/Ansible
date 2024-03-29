#vagrant_Ansible
This repo contains the configuration steps, provisioning VMs, ssh connection b/w boxes and ansible ping

#jenkins Links to cron job & email notification

#https://www.lenar.io/jenkins-schedule-build-periodically/

#https://stackoverflow.com/questions/25341198/javax-mail-authenticationfailedexception-is-thrown-while-sending-email-in-java

#Ansible

http://people.redhat.com/mlessard/qc/presentations/Mai2016/AnsibleWorkshopNA.pdf (Detailed introduction)

# What you did with Ansible?
1. I worked on with various modules that comprise of both cloud & shell modules.
2. Ansible verion 2.7/2.8 where I developed palybooks from scratch to provision the services on AWS cloud ans used shell modules while working on Linux based systems.
3. Apart of provisioning, I have utilized ansible for automation & configuing services based on roles, patching servers, removing dead computer objects, adding users/permissions, copying files      from server-server/buckets in diff region.
4. Also, worked with Ansible-Vault for Encrypt/decryption over the servers when dealing with sensitive data like sshkeys/passwords.
5. Good exposure with Ansible Towers Dashboard which is an GUI is very user friendly..involved in integrating the source code (gitHub) where playbook resides, creating Jobs, Templates, setting up User.group permissions, Inventories, Variables).
6. Once setup is done on tower, I have to ensure one push of a button deployment.

Rocket chip

# Ansible Major Components
Ansible Controller Machine, Inventories, Modules, Variables,Facts,Plays,Playbooks,Configuration files, roles, tasks.

Inventory: /etc/ansible/hosts

Handlers: used to trigger the status of the service such as restarting or stopping service

# ad-hoc commands
simple one line command used to perform a certain task ( ansible-playbook <playbook-name> ).
  
# copying files recursively
1. yes, copy module and recursive pareter set to yes.
2. syncronize module

# Ansible shell vs Command module.
Shell: It is almost exactly like the command module but runs the command through a shell (/bin/sh) on the remote node.

Command: The command(s) will not be processed through the shell, so variables like $HOME and operations like "<", ">", "|", ";" and "&" will not work. Use the shell          module if you need these features.
  
# Yaml Syntax points to remember"
  All YAML files (regardless of their association with Ansible or not) can optionally begin with --- and end with ... . This is part of the YAML format and indicates the start and end of a document.
  https://github.com/chsiva/AWS/blob/master/ec2_provision.yml
  
  https://docs.ansible.com/ansible/latest/reference_appendices/YAMLSyntax.html
  

# Playbook vs Tasks vs Roles

1. Playbook: organize and launch tasks. Playbook will be contain everything for ex: roles, tasks

2. Task: To do stuff like  a step that execute based on the inputs given. see example below
- name: Update db servers
  hosts: databases
  remote_user: root

  tasks:
  - name: Ensure postgresql is at the latest version
    ansible.builtin.yum:
      name: postgresql
      state: latest

3. Roles: 
Role is a set of tasks and additional files to configure host to serve for a certain role and can be re usable by putting the functionality into generalized "libraries" that can be then used in any playbook as needed. For example see below
- hosts: webservers
  roles: this is list of roles to assign to these hosts
     - common
     - webservers
Note: webservers - this group of hosts defined in /etc/ansible/hosts, databases and mail_servers in example from your question

# Ansible-vault
https://www.golinuxcloud.com/ansible-vault-example-encrypt-string-playbook/
