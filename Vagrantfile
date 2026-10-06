Vagrant.configure("2") do |config|

  config.vm.box = "debian/bookworm"

  config.vm.define "dhcp" do |srv|
    srv.vm.hostname = "dhcp"

    srv.vm.network "public_network", bridge: "enp4s0"

    srv.vm.network "private_network",
      ip: "192.168.57.10",
      virtualbox__intnet: "intnet"
  end

  config.vm.define "c1" do |c1|
    c1.vm.hostname = "c1"

    c1.vm.network "private_network",
      type: "dhcp",
      virtualbox__intnet: "intnet"
  end

  config.vm.define "printer" do |printer|
    printer.vm.hostname = "printer"

    printer.vm.network "private_network",
      :mac => "02:7a:c9:24:46:59",
      type: "dhcp",
      virtualbox__intnet: "intnet"
  end
end