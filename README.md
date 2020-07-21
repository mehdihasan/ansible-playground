## Getting Started

Ansible is a very lightweight configuration management tool that uses YAML files to define the state of a system.

Playbooks consist of tasks, which are entries that designate a single action. These tasks can be grouped together into roles, which can in turn be grouped into plays. The goal of a play is to take a set of roles and apply them to a specific set of machines. These roles will run multiple tasks, ensuring that the state of each machine is how you expect it to be.

The Ansible documentation for playbooks is excellent, and it should always be your first point of reference for playbook syntax (http://docs.ansible.com/ansible/index.html).

If you want to jump straight in and see some sample playbooks, there are lots of them available in the ansible-examples repository on Github (https://github.com/ansible/ansible-examples).

You've used Vagrant and VirtualBox to create a test environment, and provisioned it using vagrant provision, but by using the ansible-playbook command (covered in the next chapter), you can run your playbook against any machine that has a running SSH server. In the next chapter, we'll be taking a deeper look at the inventory, a file that tells Ansible where to run, which user to log in as, and more.

## References

1. [first point of reference for playbook syntax](http://docs.ansible.com/ansible/index.html)
2. [ansible-examples](https://github.com/ansible/ansible-examples)
