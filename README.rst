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

