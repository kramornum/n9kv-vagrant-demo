# Vagrant Cisco NX-OSv 
This repository contains a couple of demos showing how to use the puppet and ansible tools to manage Open NX-OS. These are based on the virtual Nexus 9000 and use Vagrant for provisioning the demo/test environments.
## Requirements
The demos assume the following requirements:

* Vagrant (tested on 1.8.7)
* VirtualBox (tested with 5.1.20)
* NX-OSv box added to your vagrant: 
    * Download the .VMDK file from [CCO]("https://software.cisco.com/download/release.html?mdfid=286312239&flowid=81422&softwareid=282088129&release=7.0(3)I5(1)&relind=AVAILABLE&rellifecycle=&reltype=latest")
    * Follow the instructions [here](http://www.cisco.com/c/en/us/td/docs/switches/datacenter/nexus9000/sw/7-x/nx-osv/configuration/guide/b_NX-OSv_9000/b_NX-OSv_chapter_01.html#reference_BAD5B5587C6B45AAB2FA462759DCCBD0) (the sections titled "Creating a VM in a VirtualBox Environment" through "Set Up SSH Passwordless Connection to VM").
    * Export to a .box file: `vagrant package --base n9kv --output n9kv.box`
    * Add to vagrant: `vagrant box add --name nxosv/7-0-3-i5-2 n9kv.box`
    * Verify: Run `vagrant box list` and look for `nxosv/7-0-3-i5-2                  (virtualbox, 0)`

## Available Demos
The following demos are currently available in this repository:

* **Puppet**: Sets up a Puppet master server and two virtual Nexus 9000 switches, each with the Puppet agent installed and configured to use the master. 
