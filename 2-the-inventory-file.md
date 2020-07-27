# The Inventory File

## Objective

- ansible-playbook command
- inventory file

## Concepts

ansible-playbook -i <inventory_file> provisioning/playbook.yml

## ToDo 01

edit your vagrantfile and enable private networking so that you can SSH into the machine. This is done by opening up the vagrantfile in your editor and uncommenting line 29 (config.vm.network "private_network").

```bash
vagrant halt && vagrant up
```

create a sample inventory file. It contains the IP address of the machine to connect to, which user to log in as, and the path to a private key file to use.

```bash
cd ansible-book
nano inventory
```

paste the following content there

```txt
192.168.33.10 ansible_user=vagrant ansible_ssh_private_key_file=.vagrant/machines/default/virtualbox/private_key
```

now run ansible from your machine to the remote machine with the following command

```bash
ansible-playbook -i inventory provisioning/playbook.yml
```
