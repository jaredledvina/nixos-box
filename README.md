# nixos-box

This repo contains a basic [NixOS](https://nixos.org/) Packer and Vagrant setup to allow for 
local NixOS work without having to do a full install. 

## How to use this repo
1. Install Packer: https://www.packer.io/docs/install/index.html
2. Install Vagrant: https://www.vagrantup.com/docs/installation/
3. `git clone` this repo locally and `cd` into it
4. `cd packer`
5. `packer build -force nixos.json`
6. `cd ..`
7. `vagrant up`
8. `vagrant ssh`

To debug/step through the Packer build, use `packer build -force -debug nixos.json`
Alternatively, if you want to be prompted only on failures. use ` packer build -on-error=ask -force nixos.json`

To force a full rebuild and reset Vagrant:
1. `rm -rf packer/{nixos.box,nixos.box.checksum,output-virtualbox-iso}`
2. `vagrant box remove --all --force nixos-box`
3. Follow the build steps above
