# -*- mode: ruby -*-
# vi: set ft=ruby :

require 'yaml'
vagrant_config = YAML.load_file("provisioning/virtualbox.conf.yml")

Vagrant.configure("2") do |config|

  # Bring up the Devstack controller node on Virtualbox
  config.vm.define "docker_vm" do |docker_vm|
    docker_vm.vm.provider :docker do |d|
      d.name = 'my-container'
      d.build_dir = "."
      d.cmd = ["ping", "-c 51", "127.0.0.1"]
      d.remains_running = true
      d.vagrant_machine = "docker_vm"
      d.vagrant_vagrantfile = "./dockerhostVagrantfile"
    end
  end
end
