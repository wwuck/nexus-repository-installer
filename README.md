About
-----

Package Nexus Repository Manager 3 as an RPM.

Overview
--------

Make is used to download the application bundle from Sonatype, populate an RPM build
environment, and invoke `rpmbuild`.
You can specify the bundle version to download by setting the `VERSION` environment variable 
The RPM will be written to `./build`.

```
$ make build
$ VERSION=3.15.2-01 make rpm
```

Build the RPM in a docker container.  The RPM will be written to `build/`.

```
$ make docker
$ VERSION=3.15.2-01 make docker
```

Use the `make help` command to see more options.

Tweaks made to the Application
------------------------------

* Software installs to */opt/sonatype/nexus3*.

* Patch nexus.properties: The `data directory` is */opt/sonatype/sonatype-work/nexus3*.


Notes/Todo
----------

* ~~Currently, the service daemon (linked to `/etc/init.d/nexus3`) is NOT started after install.~~
  
  ~~Similarly, the service daemon is NOT stopped before upgrade or remove.~~
  
  ~~Therefore, you need to stop/start the service manually. Patches to improve this behavior are welcome!~~
  * Done: The .rpm will now start Nexus Repository Manager after installation, and stop and restart during upgrade.
  
* Add an installer for .deb packaging  

## The Fine Print

It is worth noting that this is **NOT SUPPORTED** by Sonatype, and is a contribution to the open source community (read: you!)

Don't worry, using this community item does not "void your warranty". In a worst case scenario, you may be asked to 
remove the community item by the Sonatype Support team in order to determine the cause of any issues.

Remember:

* Use this contribution at the risk tolerance that you have
* Do **NOT** file Sonatype support tickets with Sonatype support related to this project
* **DO** file issues here on GitHub, so that the community can pitch in

Phew, that was easier than I thought. Last but not least of all:

Have fun building and using this item, we are glad to have you here!

## Getting help

Looking to contribute, but need some help? There's a few ways to get information:

* Chat with us on [Gitter](https://gitter.im/sonatype/nexus-developers)
* Check out the [Nexus3](http://stackoverflow.com/questions/tagged/nexus3) tag on Stack Overflow
* Check out the [Nexus Repository User List](https://groups.google.com/a/glists.sonatype.com/forum/?hl=en#!forum/nexus-users)
