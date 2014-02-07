.. contents::

Introduction
============

Templates for OpenBSD stuff

**mr.bobby** templates : http://mrbobby.readthedocs.org/en/latest/

+ carp_iface : provide carp ifaces master and slave which could be based on a vlan interface

  ::

    --> cidr ip: 192.168.1.1/24
    
    --> vhid: 42
    
    --> slave advskew: 100
    
    --> description: Router Interface
    
    --> password: secret
    
    --> physical device card name: em0
    

.. note:: here vlan default value is based on vhid
   
  ::
    
    --> vlan id (1 to 4094,  0 -> no vlan carpdev) [42]:
    
    --> master hostname: charybde
    
    --> slave hostname: scylla
    
    --> carp_group hostname: ha
    
which generate ::

    ├── charybde
    │   └── etc
    │       ├── hostname.carp42
    │       └── hostname.vlan42
    └── scylla
        └── etc
            ├── hostname.carp42
            └── hostname.vlan42

::
 
    $ cat charybde/etc/hostname.carp42
    inet 192.168.1.1 255.255.255.0 192.168.1.255 vhid 42 carpdev vlan42 pass secret group ha description "Router Interface"
    # subnet : 192.168.1.0/24
    $ cat charybde/etc/hostname.vlan42
    vlandev em0
    $ cat scylla/etc/hostname.carp42
    inet 192.168.1.1 255.255.255.0 192.168.1.255 vhid 42 carpdev vlan42 advskew 100 pass secret group ha description "Router Interface"
    # subnet : 192.168.1.0/24
    $ cat scylla/etc/hostname.vlan42
    vlandev em0

Documentation
=============

http://bobbytemplatesopenbsd.readthedocs.org/


Tests
=====

bobbytemplates.openbsd is continuously 

+ tested on Travis |travisstatus|_ 

+ coverage tracked on coveralls.io |coveralls|_.


.. |travisstatus| image:: https://api.travis-ci.org/jpcw/bobbytemplates.openbsd.png?branch=master
.. _travisstatus:  http://travis-ci.org/jpcw/bobbytemplates.openbsd


.. |coveralls| image:: https://coveralls.io/repos/jpcw/bobbytemplates.openbsd/badge.png
.. _coveralls: https://coveralls.io/r/jpcw/bobbytemplates.openbsd

