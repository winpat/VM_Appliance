Virtual Machine Appliance Build
===============================
This directory contain all resources required to build CentOS virtual machine appliances.

Requirements
------------
To build an virtual machine image the following tools are needed:
* Packer
* VirtualBox
* Make

> To develop and debug ansible roles it recomended to also have vagrant installed

Build Steps
-----------
The build consists of the following steps:
1. CentOS base installation through the Kickstart file.
2. Shell provisoner to bootstrap Ansible
3. Ansible provisioner to provision the virtual machine
4. Shell provisoner to install VirtualBox guest additions
5. Compress post-processor to compress .ova file

Known Issues
------------
* Don't run the build as root user. Ansible will fail with an "You need to be root to perform this
  command.". The root cause for this is unclear.
