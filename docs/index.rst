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

    $ ln -s ~/rpmbuild_supervisor/.rpmmacros ~/.rpmmacros


#. Download Supervisor 3.3.1 from `GitHub`::

    $ curl -L -o ~/rpmbuild_supervisor/rpmbuild/SOURCES/supervisor-3.3.1.tar.gz \
        https://github.com/Supervisor/supervisor/archive/3.3.1.tar.gz

#. RPM build Supervisor 3.3.1::

    $ cd ~/rpmbuild_supervisor/rpmbuild/SPECS/
    $ rpmbuild -ba supervisor.spec


#. Copy RPM/SRPM packages::

    $ cp ~/rpmbuild_supervisor/rpmbuild/RPMS/noarch/supervisor-3.3.1-1.noarch.rpm /tmp/
    $ cp ~/rpmbuild_supervisor/rpmbuild/SRPMS/supervisor-3.3.1-1.src.rpm /tmp/


#. Clean up rpmbuilder account::

    $ exit
    $ sudo userdel -r rpmbuilder


Installing
==========

#. Install Supervisor-3.3.1 with yum::

    $ yum install /tmp/supervisor-3.3.1-1.noarch.rpm
