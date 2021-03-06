testable_javascript_setup
=========================

This is a companion project to Patrick Delancy's Test Driven Development JavaScript Workshop (https://github.com/PatrickDelancy/TddJavaScriptWorkshop). This project allows you to quickly setup a virtual machine properly provisioned to support starting the workshop.

Requirements
-------------
This method of set up has three requirements of it's own, but with these requirements you can set up many different development environments in the future.

1. Vagrant (version 1.5.2 or later) - http://www.vagrantup.com/downloads.html
2. VirtualBox or VMWare - https://www.virtualbox.org/wiki/Downloads
3. Ansible Core - http://docs.ansible.com/intro_installation.html#installing-the-control-machine
4. Git - http://git-scm.com/downloads

Vagrant will automatically detect VirtualBox or VMWare, as long as one or the other is installed, and Vagrant will also automatically detect Ansible.

How to Use
-----------

Open a terminal, and run the following::

	cd ~
	git clone https://github.com/edthedev/testable_javascript_setup.git
	cd ~/testable_javascript_setup
	vagrant box add centos6 https://github.com/2creatives/vagrant-centos/releases/download/v6.5.1/centos65-x86_64-20131205.box 
	vagrant up

Now is a good time to get a cup of coffee, introduce yourself to your neighbor. It will take a few minutes to create the virtual machine and install the workshop prerequisites.

You should now have the workshop starting source code checked out at `~/testable_javascript_setup/TddJavaScriptWorkshop`. 

Now open a browser to `127.0.0.1:8080`. You should see the welcome page for the application.::

	If you can read this, then javascript is loaded and running correctly.
	If you can also read this, then stylesheets are compiling correctly, too!

If you need to stop or restart the gulp server inside your virtual machine::

	cd ~/testable_javascript_setup
	vagrant ssh
	sudo killall gulp
	cd /vagrant
	gulp serve

When you're finished with the workshop, you can clean up the virtual machine you created.::

	cd ~/testable_javascript_setup
	vagrant halt
	vagrant destroy

