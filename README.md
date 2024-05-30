# Ubuntu 22.04 environment setup for ARO w/ MSFT Intune

## Prerequisites

Ubuntu 22.04 with disk encryption.

Install ansible and git
```
sudo apt-get install ansible git
```

## Run the playbook

Clone this repo and run the play `site.yml` to configure your environment.  --ask-become-pass is only required for the first execution.
```
ansible-playbook site.yml --ask-become-pass -e=username=$USER
```



# Post playbook setup 
## Setup Intune
After the playbook completes open microsoft edge and accept any agreements, then open Intune and login to complete device setup and registration.

## Install golang
The playbook sets up go environment variables but does not install it, install it using:
```
wget https://go.dev/dl/go1.20.14.linux-amd64.tar.gz
sudo rm -rf /usr/local/go && sudo tar -C /usr/local -xzf go1.20.14.linux-amd64.tar.gz
rm go1.20.14.linux-amd64.tar.gz
```
