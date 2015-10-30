# Vagrant Box Provisioning for an Elixir Environment

## Stack

With this provision, you get the following stack:

* Update apt packages
* Basic packages (eg. curl, git, etc)
* Elixir
* Erlang

**PS**: This whole README assumes a Mac OS X setup. Please feel free to contribute if you would like to add support for other platforms.

## Getting started

What you need to do:

* clone and setup repo
* setup vagrant box
* package vagrant box
* add vagrant box to list
* use vagrant box

### Prerequisites

* Command line tools for Xcode
* [Brew](http://brew.sh/)
* [Cask](http://caskroom.io/) (brew utility to install apps/binaries like VirtualBox)
* [Vagrant](https://www.vagrantup.com/)
* [VirtualBox](https://www.virtualbox.org/)
* [Ansible](http://www.ansible.com/)

Once you have `brew` installed you can just run the following commands:

```
brew cask install virtualbox
brew cask install vagrant
brew install ansible
```

and voila!

### Repo setup

```
git clone [insert repo here]
cd [repo name]
mkdir pkg
```

### Setup Vagrant Box

All you need to do here is load the Vagrant box:

```
vagrant up --provision
```

### Package & Add Vagrant Box

```
vagrant package --output pkg/[name-of-box]
vagrant box add --name [name-of-box] pkg/[name-of-box]
```

**Example:**

```
vagrant package --output pkg/elixir
vagrant box add --name elixir pkg/elixir
```

### Double check

To make sure all worked properly you can list the local boxes you have:

```
$ vagrant box list
[name-of-box]   (virtualbox, 0)
ubuntu/trusty64 (virtualbox, 14.04)
```

**Example:**

```
$ vagrant box list
elixir            (virtualbox, 0)
ubuntu/trusty64 (virtualbox, 14.04)
```

### Use Vagrant Box

