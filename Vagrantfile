Vagrant.configure("2") do |config|
  config.vm.provider "virtualbox" do |v|
    v.memory = 4096
    v.cpus = 2
  end

  config.vm.box = "ubuntu/bionic64"
  config.vm.network "forwarded_port", guest: 80, host: 8081

  config.vm.provision "docker" do |docker|
    docker.build_image "/vagrant",
      args: "--file /vagrant/docker/Dockerfile -t hello-spa"
    docker.run "hello-spa",
      image: "hello-spa:latest",
      args: "-p 80:80"
  end
end
