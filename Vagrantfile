# -*- mode: ruby -*-
# vi: set ft=ruby :

# Vagrant.configure("2") do |config|
#   config.vm.provider "vmware_desktop" do |v|
#     # Specify VM settings
#     v.vmx["memsize"] = "2048"
#     v.vmx["numvcpus"] = "2"
#   end

#   # Attach to a host-only network with a static IP
#   config.vm.network "private_network", type: "dhcp"
#   config.vm.network "private_network", type: "static", ip: "192.168.33.200", virtualbox__intnet: "vagrant-hostonly-net"
  
#   config.vm.disk :disk, name: "backup", size: "10GB"

#   # # Add a 1 GB hard disk
#   # config.vm.provider "vmware_desktop" do |v|
#   #   v.vmx["sata0:1.present"] = "TRUE"
#   #   v.vmx["sata0:1.fileName"] = "1GB.vmdk"
#   #   v.vmx["sata0:1.size"] = "1GB"
#   # end


#   config.vm.box = "roboxes-x64/rhel9"
# end


# Vagrant.configure("2") do |config|
#   config.vm.provider "vmware_desktop" do |v|
#     # Specify VM settings
#     v.vmx["memsize"] = "2048"
#     v.vmx["numvcpus"] = "2"
#   end

#   # Attach to a host-only network with a static IP
#   config.vm.network "private_network", type: "dhcp"
#   config.vm.network "private_network", type: "static", ip: "192.168.33.201", virtualbox__intnet: "vagrant-hostonly-net"

#   # Add a 1 GB hard disk
#   config.vm.provider "vmware_desktop" do |v|
#     v.vmx["sata0:1.present"] = "TRUE"
#     v.vmx["sata0:1.fileName"] = "1GB.vmdk"
#     v.vmx["sata0:1.size"] = "1GB"
#   end

#   # Add another 2 GB hard disk
#   config.vm.provider "vmware_desktop" do |v|
#     v.vmx["sata0:2.present"] = "TRUE"
#     v.vmx["sata0:2.fileName"] = "2GB.vmdk"
#     v.vmx["sata0:2.size"] = "2GB"
#   end

#   config.vm.box = "roboxes-x64/rhel9"
# end



Vagrant.configure("2") do |config|
  (1..5).each do |i|
    config.vm.define "vm#{i}" do |node|
      node.vm.provider "vmware_desktop" do |v|
        # Specify VM settings
        v.vmx["memsize"] = "2048"
        v.vmx["numvcpus"] = "2"
      end

      # Attach to a host-only network with a static IP
      node.vm.network "private_network", type: "dhcp"
      node.vm.network "private_network", type: "static", ip: "192.168.33.2#{i}", virtualbox__intnet: "vagrant-hostonly-net"

      # Add a 1 GB hard disk
      node.vm.provider "vmware_desktop" do |v|
        v.vmx["sata0:1.present"] = "TRUE"
        v.vmx["sata0:1.fileName"] = "1GB_#{i}.vmdk"
        v.vmx["sata0:1.size"] = "1GB"
      end

      # # Add another 2 GB hard disk
      # node.vm.provider "vmware_desktop" do |v|
      #   v.vmx["sata0:2.present"] = "TRUE"
      #   v.vmx["sata0:2.fileName"] = "2GB_#{i}.vmdk"
      #   v.vmx["sata0:2.size"] = "2GB"
      # end

      node.vm.box = "roboxes-x64/rhel9"
    end
  end
end
