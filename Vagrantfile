VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|

  (1..1).each do |i|
    config.vm.define "node#{i}" do |subconfig|
      subconfig.vm.box = "ubuntu/xenial64"
      subconfig.vm.provider "virtualbox" do |v|
        v.memory = "1024"
      end
      subconfig.vm.network "forwarded_port", guest: 80, host: "808#{i}"
      subconfig.vm.provision :ansible do |ansible|
        ansible.playbook = "playbook.yml"
      end
    end
  end
end
