Vagrant.configure("2") do |config|

  # Ansible Control Node
  config.vm.define "ansible-control" do |ansible_config|
    ansible_config.vm.box = "bento/ubuntu-18.04"
    ansible_config.vm.hostname = "ansible-control"
    ansible_config.vm.network "private_network", ip: "172.16.1.2"
  end

  # Webserver Node
  config.vm.define "webserver" do |webserver_config|
    webserver_config.vm.box = "bento/ubuntu-18.04"
    webserver_config.vm.hostname = "webserver"
    webserver_config.vm.network "private_network", ip: "172.16.1.3"
  end

end
