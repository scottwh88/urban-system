# -*- mode: ruby -*-
# vi: set ft=ruby :

# Created by Scott Whitehead
# 28/10/2018
# Deploy and provision 3 servers


Vagrant.configure("2") do |config|

    ### CentOS 7 - web01 - Web Server

        config.vm.define "web01" do |web01|
            web01.vm.box = "centos/7"
            web01.vm.hostname = "web01"
            web01.vm.network "private_network", ip: "192.168.33.11"
            web01.vm.synced_folder '.', '/vagrant', disabled: true
        end

    ### CentOS 7 - web02 - Web Server

        config.vm.define "web02" do |web02|
            web02.vm.box = "centos/7"
            web02.vm.hostname = "web02"
            web02.vm.network "private_network", ip: "192.168.33.12"
            web02.vm.synced_folder '.', '/vagrant', disabled: true
        end

    ### CentOS 7 - lb01 - Load Balancer

        config.vm.define "lb01" do |lb01|
            lb01.vm.box = "centos/7"
            lb01.vm.hostname = "lb01"
            lb01.vm.network "private_network", ip: "192.168.33.13"
            lb01.vm.synced_folder '.', '/vagrant', disabled: true
        end
    end