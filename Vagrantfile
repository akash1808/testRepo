# -*- mode: ruby -*-
# vi: set ft=ruby :
Vagrant.configure("2") do |config|

  location = ENV['LOCATION']
  hostaddresses = ENV['HOSTIPADDRESSES']
  [location = "M3OFFICE" ] if (location.nil?)
  [hostaddresses = "127.0.1.1" ] if (hostaddresses.nil?)

  databagfile = "../databags/#{location}.json"
  keyfile = "../databags/key.json"
  config.vm.box = "precise64"
  config.vm.box_url = "http://cloudcto.wipro.com/vagrantboxes/precise64.box"
  config.vm.network :forwarded_port, guest: 3001, host: 3001, auto_correct: true
  config.vm.network :forwarded_port, guest: 22, host: 2224, auto_correct: true
  config.vm.network :public_network, :use_dhcp_assigned_default_route => true
  var="1js"
  config.vm.hostname=var
  config.vm.provider "virtualbox" do |v|
     v.name = var
     v.customize ["modifyvm",:id,"--memory",2048]
     v.customize ["modifyvm", :id, "--cpus", "2"] 
     v.customize ["modifyvm", :id, "--ioapic", "on"]
  end
  end
hello

