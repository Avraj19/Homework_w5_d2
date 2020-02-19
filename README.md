# Vagrant lab

## Timings

This lab should take 60 - 90 minutes to complete

## Summary

The development team are happy to use your vagrant machine to work on. But they all need to install it on their machines and to know how it works.

> NOTE TO INSTRUCTOR: All students should fork the node sample app available on the Sparta Global Github.

In your fork of the node-sample-app: `https://github.com/spartaglobal/node-sample-app`

## Tasks

1. Create a vagrant file that creates the machine as we did in the previous lesson.

2. Add to the README.md instructions that explain the steps the developer will need to go through to use this environment i.e they'll need to install vagrant and virtual box, install all the plugins and know where to put their app code.

3. Swap repos with another team and test theirs to make sure the instructions are clear and all the files are included.

## Bonus Task

* The goal is that the developers should be able to simply clone your repo and run "vagrant up". Can you automate the installation of the required vagrant plugins?

> NOTE: At the moment we only expect our vagrant machine to display the nginx test page. We will move on to running the app in this environment in a following lesson


## How to create a vagrant file with VM
steps:
1. Go to https://www.vagrantup.com/
2. Download and install the most up to date version, it should be 2.27
3. Go to https://www.virtualbox.org/wiki/Downloads
4. Download 
- In documents create a file 
- Open gitbash on the file 
Type in the following command in order and as you see them:
1. vagrant init ubunto/bionic64 - this sets up a vagrant file
    - open vagrant file in your folder
    - replace with:
Vagrant.configure("2") do |config|
  config.vm.box = "ubuntu/bionic64"
  
  config.vm.provider "virtualbox" do |v|
     v.customize ["modifyvm", :id, "--natdnshostresolver1", "on"]
     v.customize ["modifyvm", :id, "--natdnsproxy1", "on"]
   end
end

2. vagrant up - this launches the virtual machine (VM)
3. vagrant ssh - this create a private key the access the VM
4. sudo apt-get update - gets upgrades for ubuntu
5. sudo apt-get upgrade - compairs version of updates with current gets 
6. sudo apt-get install - installs upgrades that are 