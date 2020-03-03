Vagrant.configure("2") do |config|
  config.vm.define "nodejs" do |v|
    v.vm.provider "docker" do |d|
      d.build_dir = "."
      d.ports = ['3000:3000']
    end
  end
end
