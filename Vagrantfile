Vagrant.configure("2") do |config|

  config.vm.box = "ubuntu/trusty64"
  config.vm.hostname = "devops-playbooks"
  config.ssh.forward_agent = true

  # Forward guest port 8787 to host port 8787 (for RStudio)
  config.vm.network "forwarded_port", guest: 8787, host: 8787

  config.vm.provision "file", source: "~/.ssh/config", destination: "~/.ssh/config"

  config.vm.provider :virtualbox do |vb|
    vb.name = Dir.pwd().split("/")[-1] + "-" + Time.now.to_f.to_i.to_s
    vb.customize ["modifyvm", :id, "--natdnshostresolver1", "on"]
    vb.customize [ "guestproperty", "set", :id, "--timesync-threshold", 10000 ]
    vb.memory = 10240
  end

  config.vm.provision :shell do |sh|
    sh.path = "vagrant/up.bash"
  end

