Lab Environment & Topology 
==========================

.. NOTE:: All work is done from the Linux client/jumphost (client01), which can
   be accessed via RDP (Windows Remote Desktop) or ssh. No installation or
   interaction with your local system is required.

Environment
-----------

**Linux client (client01):**

**Web Attack Tools used in this lab:**

- `BURP Community Edition <https://portswigger.net/burp/>`_ - Packet Crafting
- `curl <https://curl.haxx.se/>`_ - command line webclient. Very useful for debugging and request crafting

**Linux server (server01):**

- `WebGoat 8 <https://github.com/WebGoat/WebGoat/wiki>`_ - WebGoat is a deliberately insecure web application maintained by OWASP designed to teach web application security lessons. The primary goal of the WebGoat project is simple: create a de-facto interactive teaching environment for web application security.

Lab Topology
------------

The network topology implemented for this lab is very simple, since the
focus of the lab is Control Plane programmability rather than Data Plane
traffic flow we can keep the data plane fairly simple. The following
components have been included in your lab environment:

-  1 x Ubuntu Linux 18.04 client, with client tools installed - aptly named: client01
-  1 x F5 BIG-IP VE (v15.1.0.1) running ASM and LTM - aptly named: bigip01
-  1 x Ubuntu Linux 18.04 server, with webgoat 8 installed - aptly named: server01 

.. nwdiag:: labtopology.diag
   :width: 800
   :name: lab-topology-diagram
   :scale: 110%

The following table lists VLANS, IP Addresses and Credentials for all
components:

.. list-table::
   :widths: 15 15 15 15 15 
   :header-rows: 1


   * - **Component**
     - **mgmtnet IP**
     - **clientnet IP**
     - **servernet IP**
     - **Credentials**
   * - Linux Client (client01)
     - 10.1.1.51
     - 10.1.10.51
     - N/A
     - https-``f5student:f5DEMOs4u!``
   * - Bigip (bigip01)
     - 10.1.1.245
     - 10.1.10.245
     - 10.1.20.245
     - https - ``admin:f5DEMOs4u!`` ssh - ``f5student:f5DEMOs4u!``
   * - Linux Server (server01)
     - 10.1.1.252
     - N/A
     - 10.1.20.252
     - ssh - ``f5student:f5DEMOs4u!``

.. note:: External links are not required reading for the lab, rather
   supplemental if you you would like to get a different take or
   additional info.

.. note:: Replace all instances of <bigip> with the management ip of the
   bigip1, 10.1.1.245. The $password referenced in the curl commands is an
   environment variable, there is no need to modify it. 
