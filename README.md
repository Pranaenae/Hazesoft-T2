# Hazesoft-T2

## 1.Setup the environment for running ansible commands. 
I am only creating a control node and a webserver node using Vagrant.

```
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
```
![image](https://github.com/Pranaenae/Hazesoft-T2/assets/80820244/8d67767c-d855-4c90-ad3a-09440788460f)

## 2. Open the ansible-control and install ansible and other required dependencies.

Update the apt-get cache.

![image](https://github.com/Pranaenae/Hazesoft-T2/assets/80820244/920ed865-b638-46e4-a33d-8ad092255fff)

Install ansible.

![image](https://github.com/Pranaenae/Hazesoft-T2/assets/80820244/a5a9cc67-f92f-4f0c-a0f6-75981077171f)

Install vim.

![image](https://github.com/Pranaenae/Hazesoft-T2/assets/80820244/92bcb7b9-87f2-4501-a233-b720e909be4d)

## 3. Modify the hosts file in ansible to include the ansible-control and webserver.

```
sudo vim /etc/hosts
```

![image](https://github.com/Pranaenae/Hazesoft-T2/assets/80820244/9bd9ad1a-1152-415e-9ed6-bd09e6690c4f)

## 4. Generate an ssh key to connect to the target webserver.

![image](https://github.com/Pranaenae/Hazesoft-T2/assets/80820244/17c0157d-ae9e-4464-8801-a9ee34e08241)

Copy the ssh key to the webserver.

![image](https://github.com/Pranaenae/Hazesoft-T2/assets/80820244/e8e37d6d-02ba-46a8-91d3-afb18fb3bbbb)

Pinging and ssh to webserver target.


