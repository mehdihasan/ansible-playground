# The Inventory File

## Table of Contents

| Title                              | Description                            |
| ---------------------------------- | -------------------------------------- |
| 1. Objective                       | [go](#objective)                       |
| 2. Concepts                        | [go](#concepts)                        |
| 3. Running Without Vagrant         | [go](#running-without-vagrant)         |
| 4. Inventory Variable Registration | [go](#inventory-variable-registration) |
| 5. Inventory Groups                | [go](#inventory-groups)                |
| 4. References                      | [go](#references)                      |

[🏠 Back to Table of Contents](#table-of-contents)

## Objective

- ansible-playbook command
- inventory file

[🏠 Back to Table of Contents](#table-of-contents)

## Concepts

- inventory file: list of host names, ssh info etc
- By default, Ansible will read /etc/ansible/hosts as its default inventory file.
- ansible-playbook -i <inventory_file> provisioning/playbook.yml
- A well-written inventory file isn't just something for Ansible to use; it's documentation about your deployment for new employees, contractors, and even for yourself when you need to refer back to it.

[🏠 Back to Table of Contents](#table-of-contents)

## Running Without Vagrant

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

[🏠 Back to Table of Contents](#table-of-contents)

## Inventory Variable Registration

Other than defining variables in the inventory file, there are some other places to define those, later which can be used in the playbook. Variables are important while we have multiple environment to work with with the same component, say like database username.

## Inventory Groups

Grouping all the similar environmens (prod, stage, dev etc) together and target those as a single entity.

[🏠 Back to Table of Contents](#table-of-contents)

## References

1. [Common Inventory Configuration Options](https://docs.ansible.com/ansible/latest/user_guide/intro_inventory.html)
2. [Patterns: targeting hosts and groups](https://docs.ansible.com/ansible/latest/user_guide/intro_patterns.html#)
3. [Working with dynamic inventory](https://docs.ansible.com/ansible/latest/user_guide/intro_dynamic_inventory.html)
