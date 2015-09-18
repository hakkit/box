# -*- mode: ruby -*-
# vi: set ft=ruby :

require "yaml"
require_relative "lib/string"

Vagrant.configure(2) do |config|

    # Load the config file.
    hakkit = YAML.load_file(".")

    # Specificy the box to use.
    config.vm.box = "ubuntu/trusty64"

    # Specify the hostname to use.
    config.vm.hostname = "hakkit"

    # Forward the necessary ports.
    config.vm.network "forwarded_port", guest: 80, host: 8080
    config.vm.network "forwarded_port", guest: 3306, host: 33060
    config.vm.network "forwarded_port", guest: 5432, host: 54320

    # Configure shared folders.
    hakkit['folders'].each do |folder|
        config.vm.synced_folder "folder['sync']", "folder['to']"
    end

end
