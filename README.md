# Bugzilla Vagrant 

A VagrantFile to install Bugzilla on Ubuntu 16.04 with Apache and sqlite. 

*Note* this installation uses SQLite as the database to simplify the
 installation. This should not be used for production installations.

### How-To
Clone this repository and run `vagrant up`

### Patches Directory
If any patch files are included in the patches folder then these will be
applied using `git am`.

### Extensions Directory
If any Bugzilla extensions are included as zip archives in the
extensions folder then these are unpacked in the Bugzilla extensions
folder on the server before 'checksetup.pl' is run.

Once the provisioning stage has completed the Bugzilla application
will be running and just needs logging in as `admin@example.com` using
password `password` (can be changed in the install-bugzilla.sh file).

The box exports the guest port 80 to localhost port 8080 so the final
URL to access your Bugzilla application will be:

    http://localhost:8080/Bugzilla/
