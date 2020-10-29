#vagrant_Ansible
This repo contains the configuration steps, provisioning VMs, ssh connection b/w boxes and ansible ping

#jenkins Links to cron job & email notification

#https://www.lenar.io/jenkins-schedule-build-periodically/

#https://stackoverflow.com/questions/25341198/javax-mail-authenticationfailedexception-is-thrown-while-sending-email-in-java

#Ansible

http://people.redhat.com/mlessard/qc/presentations/Mai2016/AnsibleWorkshopNA.pdf (Detailed introduction)

# What you did with Ansible?
1. I worked on Ansible verion 2.7/2.8 where I developed palybooks from scratch to provion the services on cloud.
2. utilized ansible for automation & configuing services based on roles, patching servers, removing dead computer objects, adding users/permissions, copying files      from server-server/buckets in diff region.
3. worked with Ansible-Vault to Encrypt sshkeys/passwords.
4. Also worked on Ansible Towers (Dashboard, GUI is very user friendly..we can see Jobs, Templates, Rocket Chip, User.group permissions, Inventories, Variables).

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

