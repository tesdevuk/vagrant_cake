Vagrant::Config.run do |config|
    config.vm.host_name = "api"
    config.vm.box = "lucid32"
    config.vm.box_url = "http://files.vagrantup.com/lucid32.box"
    config.vm.forward_port 80, 8080
    config.vm.synced_folder "C:/_DEV/vagrant-cakephp/www", "/home/vagrant/www/", id: "vagrant-root", :nfs => false,:mount_options => ["dmode=777","fmode=777"]
    config.vm.network :hostonly, "192.168.111.222"
    config.vm.provision :puppet do |puppet|
        puppet.manifests_path = "puppet"
        puppet.manifest_file  = "cakephp.pp"
    end
    config.vm.provider "virtualbox" do |v|
        v.gui = false
    end
end
