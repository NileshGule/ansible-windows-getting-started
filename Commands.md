###vagrant up to bring up the VMs defined in vagrantfile###
vagrant up

###create inventory file named inventory.yml###

###create web group inside Group_vars directory in a file named web.yml###

###Execute ping command test on Windows 2012 server using winrm module###
ansible web -i inventory.yml -m win_ping

##Modules##
###Execute modules from commandine###

####Execute setup module which returns setup information ####
ansible web -i inventory.yml -m setup

####Add inventory file path to ansible defaults using the ansible.cfg file, after this there is no need to provide inventory file everytime ####
ansible web -m setup

####Run raw command for returning "dir" listing####
ansible web -m raw -a "dir"

####Run raw command for returning "ipconfig" listing####
ansible web -m raw -a "ipconfig"

####find current status of windows services eg spooler####
ansible web -m win_service -a "name=spooler"

####stop the spooler service####
ansible web -m win_service -a "name=spooler state=stopped"

####verify spooler service is stopped####
ansible web -m win_service -a "name=spooler"

####start the spooler service####
ansible web -m win_service -a "name=spooler state=started"

####install a new feature using win_feature module eg. Telnet-Client####
ansible web -m win_feature -a "name=Telnet-Client state=present"

####Execute modules from playbook####

##Playbooks##

##Roles##
