# encoding: utf-8
# vim: ft=ruby

Vagrant.require_version ">= 2.2.5"

Vagrant.configure("2") do |config|

  # don't auto update Guest Additions when "vagrant up"
  # if installed vagrant-vbguest
  if Vagrant.has_plugin?("vagrant-vbguest")
    config.vbguest.auto_update = false
  end

  # settings for virtual machine
  config.vm.box = "MSEdge.Win10"
  config.vm.guest = :windows
  config.vm.communicator = :winrm
  config.vm.synced_folder ".", "/vagrant", disabled: true
  config.vm.network :forwarded_port, guest: 3389, host: 33389

  # settings for WinRM
  config.winrm.username = "IEUser"
  config.winrm.password = "Passw0rd!"

  # settings for VirtualBox provider
  config.vm.provider "virtualbox" do |vbox|

    vbox.name = "vagrant-test-ms-edge"
    vbox.gui = false
    vbox.cpus = 2
    vbox.memory = 4096
    vbox.customize [
      "modifyvm", :id,
      "--vram", 256,
      "--paravirtprovider", "hyperv"
    ]

    # use linked clone when vagrant version >= 1.8.0
    if Gem::Version.new(Vagrant::VERSION) >= Gem::Version.new("1.8.0")
      vbox.linked_clone = true
    end

  end

end
