# ansible-training
Ansible Introduction Training

[Install Ansible](http://docs.ansible.com/ansible/latest/installation_guide/intro_installation.html)

# git clone
```git clone https://github.com/michael-salo/ansible-training.git```

### VirtualBox

Let’s install VirtualBox first.

Get latest stable version from https://www.virtualbox.org/wiki/Downloads

## Vagrant
Follow the instructions here: [Vagrant installation](https://www.vagrantup.com/docs/installation/)

### Vagrant start
```vagrant up```

### Vagrant destroy
```vagrant destroy -f```

### SSH-AGENT: How to start and add vagrant identity key in order to ssh-into VMs. 
```
eval "$(ssh-agent -s)"
ssh-add ~/.vagrant.d/insecure_private_key
```

### Test Ansible: 

```ansible -m ping all```
