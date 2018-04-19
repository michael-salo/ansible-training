# -*- mode: ruby -*-
# vi: set ft=ruby :
#  locale environment variables are passed to guest
ENV["LC_ALL"] = "en_US.UTF-8"

    Vagrant.configure(2) do |config|
       config.ssh.insert_key = false
       config.vm.provider :virtualbox do |vb|
            vb.customize ["modifyvm", :id, "--memory", "512"]
            vb.gui = false
        end

        # Application server 1.
        config.vm.define "app" do |app|
            app.vm.hostname = "app1.dev.com"
            app.vm.box = "ubuntu/trusty64"
            app.vm.network "forwarded_port", guest: 80, host: 8080
            app.vm.network "forwarded_port", guest: 443, host: 8443
            app.vm.box_check_update = false
            app.vm.network :private_network, ip: "192.168.60.4"
        end

        # Database server.
         config.vm.define "db" do |db|
            db.vm.hostname = "db.dev.com"
            db.vm.box = "centos/7"
            db.vm.box_check_update = false
            db.vm.network :private_network, ip: "192.168.60.6"
        end

       # Provisioning configuration for Ansible.
       # config.vm.provision "ansible" do |ansible|
       #     ansible.playbook = "playbook.yml"
            # Run commands as root.
       #     ansible.sudo = true
       # end
    end
