Vagrant.configure("2") do |config|

  # Configure base box parameters
  config.vm.box = "designerror/windows-7"
  config.vm.define "build" do |build|
    build.vm.guest = :windows
  end

  # Port forwarding
  config.vm.network :forwarded_port, host: 4444, guest: 4444
  ## Optional: port forward WinRM and RDP to the host
  # config.vm.network :forwarded_port, guest: 3389, host: 3389
  # config.vm.network :forwarded_port, guest: 5985, host: 5985, id: "winrm", auto_correct: true


  # Provisioning
  config.vm.provision "file", source: "start.bat", destination: "C:/Users/vagrant/AppData/Roaming/Microsoft/Windows/Start Menu/Programs/Startup/start.bat"
  config.vm.provision :shell, :path => "provision.ps1"

end
