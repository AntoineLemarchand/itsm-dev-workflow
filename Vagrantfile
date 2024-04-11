ENV['VAGRANT_DEFAULT_PROVIDER'] = 'libvirt'
Vagrant.configure("2") do |config|
  config.vm.box = "debian/bookworm64"

  config.vm.provision "ansible" do |ansible|
    ansible.playbook = "playbook.yaml"
    ansible.vault_password_file = ".vaultpass"
  end

  config.vm.provider :libvirt do |v|
    v.memory = 4096
    v.cpus = 2
  end

  config.vm.define "Development" do |dev|
    dev.vm.hostname = "dev"
    dev.vm.network "private_network", ip: "192.168.56.110"
  end
end
