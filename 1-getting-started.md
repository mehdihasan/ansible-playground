1. download & install virtualbox & vagrant.

2. run the following commands

```bash
VBoxManage --version

vagrant --version

mkdir ansible-book && cd ansible-book

vagrant init ubuntu/trusty64

vagrant up

vagrant status

vagrant ssh

cat /etc/issue

vagrant destroy

mkdir provisioning

touch provisioning/playbook.yml

vagrant provision
```
