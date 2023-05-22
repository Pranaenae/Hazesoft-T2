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

## 3. Modify the hosts file to include the ansible-control and webserver.

```
sudo vim /etc/hosts
```

![image](https://github.com/Pranaenae/Hazesoft-T2/assets/80820244/9bd9ad1a-1152-415e-9ed6-bd09e6690c4f)

## 4. Generate an ssh key to connect to the target webserver.

![image](https://github.com/Pranaenae/Hazesoft-T2/assets/80820244/17c0157d-ae9e-4464-8801-a9ee34e08241)

Copy the ssh key to the webserver.

![image](https://github.com/Pranaenae/Hazesoft-T2/assets/80820244/e8e37d6d-02ba-46a8-91d3-afb18fb3bbbb)

Pinging to webserver target.

![image](https://github.com/Pranaenae/Hazesoft-T2/assets/80820244/534d8dde-acaa-4884-a2de-fece643a1016)

## 5. Writing the inventory file.

![image](https://github.com/Pranaenae/Hazesoft-T2/assets/80820244/838f4056-e60b-4c53-8179-6edb61960564)

Replace the default hosts file with the inventory file.

```
sudo cp inventory /etc/ansible/hosts
```

## 6. Writing the ansible playbook.

![image](https://github.com/Pranaenae/Hazesoft-T2/assets/80820244/d0ed061b-dadd-4875-b6a4-2a57fba272eb)

## 7. Execute the ansible playbook.

![image](https://github.com/Pranaenae/Hazesoft-T2/assets/80820244/6556b003-899c-4b61-a55f-567cb1824c81)

## 8. SSH to the webserver.

![image](https://github.com/Pranaenae/Hazesoft-T2/assets/80820244/06cf4269-a0d8-4144-b454-f100bfd63d2d)

Now connected to the target machine.

## 9. Curl to the required url

![image](https://github.com/Pranaenae/Hazesoft-T2/assets/80820244/7a10b38a-cf84-4853-90dc-b1c6995f04ec)




