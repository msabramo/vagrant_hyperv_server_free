# -*- mode: ruby -*-
# vi: set ft=ruby :

$script = <<'SCRIPT'
# You can add PowerShell stuff here if you want...
echo "Executing script in Vagrantfile..."

# Uncomment this to install Cygwin (https://www.cygwin.com/)
# choco install -y cyg-get

# Uncomment this to install git
# choco install -y git

# Uncomment this to install PuTTY (http://www.chiark.greenend.org.uk/~sgtatham/putty/)
# choco install -y putty

# Uncomment this to install Python 2
# choco install -y python2

# Uncomment this to install Python 3
# choco install -y python

# Browse more chocolatey packages at https://chocolatey.org/packages
SCRIPT

Vagrant.configure(2) do |config|
  config.vm.box = "msabramo/HyperVServer2012"
  config.vm.provision "shell", inline: $script
end
