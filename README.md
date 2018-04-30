## How to use
1. Install Packer: https://www.packer.io/docs/install/index.html
2. Install Vagrant: https://www.vagrantup.com/docs/installation/
3. `cd packer`
4. `packer build -force nixos.json`
5. `cd ..`
6. `vagrant up`
7. `vagrant ssh`

To debug/step through the Packer build, use `packer build -force -debug nixos.json`
Alternatively, if you want to be prompted only on failures. use ` packer build -on-error=ask -force nixos.json`

To force a full rebuild and reset Vagrant:
1. `rm -rf packer/{nixos.box,nixos.box.checksum,output-virtualbox-iso}`
2. `vagrant box remove --all --force nixos-box`
3. Follow the build steps above
