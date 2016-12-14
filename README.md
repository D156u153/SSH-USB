# SSH-USB

Keep your SSH private keys on a USB keychain; use a script to initialize a self-destructing ssh-agent instance.

ssh-usb is a simple script that will setup a shell environment instantiated by ssh-agent. When initialized, it will load your custom keys located in a ssh_keys directory.

Usage
Setup

$ Mount your USB drive, formatted as ext4 and encrypted with LUKS
$ cd to your USB drive.
$ git clone https://github.com/Rel1k/SSH-USB.git
$ cp <your ssh keys> <path to USB> ssh-usb/ssh_keys/

Use

$ ./fob_init.sh
$ ssh <user>@<host>

A new bash shell is spawned with its environment set to use the launched ssh-agent instance. When finished and the shell is exited, ssh-agent exits along with it, ensuring your key isn't accidentally left behind on a strange workstation.
Security

Make sure any SSH key you place on a portable USB device is encrypted with a passphrase!

