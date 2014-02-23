Vagrant.configure('2') do |config|
  config.vm.hostname              = 'dev.deeeet.com'
  
  config.vm.provider :digital_ocean do |provider, override|
    override.ssh.private_key_path = '~/.ssh/id_rsa'
    override.vm.box               = 'digital_ocean'
    override.vm.box_url           = "https://github.com/smdahlen/vagrant-digitalocean/raw/master/box/digital_ocean.box"
    
    provider.client_id            = Secret.client_id
    provider.api_key              = Secret.api_key
    provider.image                = 'CentOS 6.4 x64'
    provider.region               = 'Singapore 1'
    provider.size                 = '512MB'
    provider.ca_path              = '/usr/local/opt/curl-ca-bundle/share/ca-bundle.crt'
    provider.ssh_key_name         = 'iMac'
  end

  config.vm.provision "shell", inline: "yum -y install git"
end
