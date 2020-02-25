* By default, libvirt provider is used. Previously I had used virtualbox but I don't have those settings now as I have moved to another laptop. I haven't tried to configure virtualbox provider in this laptop yet. 

* Earlier I had the box locations hardcoded as I didn't want to download the boxes each time. So you may find hardcoded references to boxes. If you find them, please subsitute them accordingly. Usually you can find boxes here: https://app.vagrantup.com/boxes/search?provider=libvirt

* The nodes.json file and Vagrantfile are the necessary tools. 

* In Fedora 30, there is a problem with QEMU that I have faced which is documented here: https://github.com/vagrant-libvirt/vagrant-libvirt/issues/958. Please add the following snippet in `~/.vagrant.d/Vagrantfile`: 

```
Vagrant.configure('2') do |config|
  config.vm.provider :libvirt do |v|
    v.qemu_use_session = false
  end
end
```

* You may be prompted for sudo password. 
