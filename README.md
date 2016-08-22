# Bugzilla Vagrant 

A VagrantFile to install Bugzilla on Ubuntu 16.04 with Apache and sqlite. The box exports the guest port 80 to localhost port 8080 so the final
URL to access your Bugzilla application will be:

    http://localhost:8080/Bugzilla/

**Note**
This installation should not be used for production installations. This installation uses SQLite as the database to simplify the installation. 

### Requirements
This installation requires [bento/ubuntu-16.04][1]

### Setup
Clone this repository and initialize Vagrant Box:

    git clone git@github.com:outofcontrol/bugzilla-vagrant.git
    vagrant up

Initialize Bugzilla:

    vagrant ssh
    cd /opt/bugzilla
    sudo perl -w checksetup.pl /tmp/bugzilla.responses to finalize installation

Once the provisioning stages have completed, the Bugzilla application
will be running and you can [log in][2] as `admin@example.com` using
password `password` (can be changed in the install-bugzilla.sh file).

### Directory
There are two empty directories that will allow you to extend and patch bugzilla. 

**Patches**
If any patch files are included in the patches folder then these will be
applied using `git am`.

**Extensions**
If any Bugzilla extensions are included as zip archives in the
extensions folder then these are unpacked in the Bugzilla extensions
folder on the server before 'checksetup.pl' is run.

### ToDo's

 - Get checksetup.pl to run properly.


[1]: https://atlas.hashicorp.com/bento/boxes/ubuntu-16.04/
[2]: http://localhost:8080/Bugzilla/
