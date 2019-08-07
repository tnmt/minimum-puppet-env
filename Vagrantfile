Vagrant.configure("2") do |config|

  config.vm.box = "bento/centos-7.3"
  config.vm.provision "shell", path: "install-puppet.sh"

  config.vm.define "test001" do |c|
    c.vm.hostname = 'test001'
    c.vm.network "private_network", ip: "172.28.128.10"
    c.vm.provision "puppet" do |puppet|
      puppet.manifest_file = 'init.pp'
      puppet.module_path = 'modules'
      #puppet.options = "--verbose --debug"
    end
  end
end
