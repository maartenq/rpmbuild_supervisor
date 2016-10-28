====================
RPM build supervisor
====================

Building
========

#. Install packages for RPM Build Environment::

    $ sudo yum install git rpm-build python-devel python-setuptools

#. Create RPM build user::

    $ sudo useradd rpmbuilder


#.  Become `rpmbuilder`::

    $ sudo su - rpmbuilder


#. Get rpm build tree from Github::

   $ git clone https://github.com/maartenq/rpmbuild_supervisor.git


#. Make a symbolic ~/.rpmmacros::

   $ ln -s ~/rpmbuild_supervisor ~/.rpmmarcros


