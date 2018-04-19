# ansible-training

Ansible Introduction Training
## PART I.
[Install Ansible](http://docs.ansible.com/ansible/latest/installation_guide/intro_installation.html)

## git clone
```git clone https://github.com/michael-salo/ansible-training.git```

## VirtualBox

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

# Part II.

### fuction to be added to .bashrc. Afterwards run: source .bashrc
```
function create_role() {
    if [ $# != 1 ] ; then
        echo "Usage: ${FUNCNAME[0]} <directory_name>"
    return 1
    fi

    mkdir -p $1/{tasks,handlers,templates,files,vars,meta,default}
    echo "---" | tee -a $1/{handlers,meta,tasks,vars,default}/main.yml
}
```
### How to create role structure via ansible-galaxy command:
```ansible-galaxy init roles/<role_name>```
[Ansible Galaxy](http://docs.ansible.com/ansible/latest/reference_appendices/galaxy.html#create-roles) 
## TODO(Part 2): 
1. Extend nginx role to be listened on IP of DB host, but no static variable, use dynamic one from facts.
2. Create mysql role for installing and configuring MYSQL on Ubuntu box.
3. Create a new php-fpm role or convert an existing playbook that you've already written into role.
4. Create a new role to configure sshd service via template on CentOS and Ubuntu.
