Vagrant.configure("2") do |config|
    config.vm.box = "precise32"
    config.vm.host_name = "api"
    config.vm.box_url = "http://files.vagrantup.com/precise32.box"
    config.vm.network :private_network, ip: "192.168.111.222"
    config.vm.network :forwarded_port, host: 8080, guest: 80
    config.vm.synced_folder "C:/_DEV/vagrant-cakephp/www", "/home/vagrant/www/", :owner => "www-data", :nfs => false,:mount_options => ["dmode=777","fmode=777"]
    
    config.vm.provision :puppet do |puppet|
        puppet.manifests_path = "puppet"
        puppet.manifest_file  = "cakephp.pp"
    end
    config.vm.provider "virtualbox" do |v|
        v.gui = false
    end
end
