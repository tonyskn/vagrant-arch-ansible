
Vagrant.configure("2") do |config|
   config.vm.box = "arch64"
   config.vm.network :private_network, ip: "192.168.111.222"

   # Configure Ansible provisionner
   config.vm.provision :ansible do |ansible|
      ansible.host_key_checking = false
      ansible.extra_vars = { ansible_python_interpreter: "/usr/bin/python2" }

      ansible.playbook = "ansible/playbook.yml"
   end
end

