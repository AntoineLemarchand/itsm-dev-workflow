ENV['VAGRANT_DEFAULT_PROVIDER'] = 'libvirt'
Vagrant.configure("2") do |config|
  config.vm.box = "debian/bookworm64"

  config.vm.provision "ansible" do |ansible|
    ansible.playbook = "playbook.yaml"
  end

  config.vm.provider :libvirt do |v|
    v.memory = 4096
    v.cpus = 2
  end
end
