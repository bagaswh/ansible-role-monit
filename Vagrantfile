# -*- mode: ruby -*-
# vi: set ft=ruby ts=2 sw=2 tw=0 et :

vmname = File.basename(File.expand_path(File.dirname(__FILE__)))

Vagrant.configure("2") do |config|

  config.vm.define "Ubuntu-24.04" do |ap|
    ap.vm.box = "alvistack/ubuntu-24.04"
    ap.vm.hostname = "Ubuntu-24.04"

    ap.vm.provider "virtualbox" do |v|
      v.customize ["modifyvm", :id, "--cpuexecutioncap", "50"]
      v.customize ["modifyvm", :id, "--memory", 512]
    end

    ap.vm.network :private_network, ip: "192.168.56.8"
    ap.vm.network :forwarded_port, guest: 2812, host: 2813

    ap.vm.provision :ansible do |ansible|
      ansible.playbook = "vagrant.yml"
    end
  end

  # config.vm.define 'Rocky9' do |ap|
  #   ap.vm.box = "rockylinux/9"
  #   ap.vm.hostname = 'Rocky9'

  #   ap.vm.provider "virtualbox" do |v|
  #     v.customize ["modifyvm", :id, "--cpuexecutioncap", "50"]
  #     v.customize ["modifyvm", :id, "--memory", 512]
  #   end

  #   ap.vm.network :private_network, ip: "192.168.56.9"
  #   ap.vm.network :forwarded_port, guest: 2812, host: 2814

  #   ap.vm.provision :ansible do |ansible|
  #     ansible.playbook = "vagrant.yml"
  #   end
  # end

end
