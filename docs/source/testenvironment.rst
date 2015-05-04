.. _testenvironment:

Software test environment
=========================

UW Tower and BHB server rooms
-----------------------------

DIMS deployments will all be hosted at the same site, currently two server room
racks at the University of Washington Tower ("UW Tower") and Benjamin Hall
Research Building ("BRB").

Each deployed system will be separated from the others and operate
independantly (in terms of services and logical network topologies).
Even if they are in the same rack and possibly sharing some fundamental
resources (e.g., Network Attached Storage (NAS), or switched VLANs,
they will each be deployed, configured, and will operate in such
a manner as to be fully taken down without impacting the operation
of the other environments.

This will allow development, test and evaluation, and user acceptance
test 

.. _softwareitems:

Software items
--------------

.. _swtable:

.. table:: Software Items Table

    +------------------------+------------------------------------------------------------+
    | Software item          | Purpose                                                    |
    +========================+============================================================+
    | `Jira`_                | Ticketing, task tracking, etc.                             |
    +------------------------+------------------------------------------------------------+
    | `Zephyr for Jira`_     | Test management plugin for `Jira`_                         |
    +------------------------+------------------------------------------------------------+
    | `Robot Framework`_     | Open source Acceptance Test-Driven Development (ATTD) tool |
    +------------------------+------------------------------------------------------------+
    | Custom DIMS scripts    | Serve specific custom test functions as needed.            |
    +------------------------+------------------------------------------------------------+

..

.. _Robot Framework: http://robotframework.org/

.. _hardwarefirmwareitems:

Hardware and firmware items
---------------------------

.. todo::

   This paragraph shall identify by name, number, and version, as applicable,
   the computer hardware, interfacing equipment, communications equipment, test
   data reduction equipment, apparatus such as extra peripherals (tape drives,
   printers, plotters), test message generators, test timing devices, test
   event records, etc., and firmware items that will be used in the software
   test environment at the test site(s). This paragraph shall describe the
   purpose of each item, state the period of usage and the number of each item
   needed, identify those that are expected to be supplied by the site, and
   identify any classified processing or other security or privacy issues
   associated with the items.

.. _hwtable:

.. table:: Hardware Items Tables

   +-----------------------------------------------+--------------------------------+
   |             Hardware Item                     |             Purpose            |
   +===============================================+================================+
   | - Dell PowerEdge R715 server                  | Server capable of running all  |
   | - 128GB RAM                                   | DIMS components in containers  |
   | - 2x12-Core 1.8GHz AMD Opteron processors     |                                |
   | - 12 x 1TB drives in RAID 5 array             |                                |
   +-----------------------------------------------+--------------------------------+
   | - Dell PowerEdge R720 server                  | Server capable of running all  |
   | - 128GB RAM                                   | DIMS components in containers  |
   | - 4x12-Core 2.40Ghz Intel Xeon E5-2695 v2     |                                |
   | - 6 x 4TB drives in RAID 5 array              |                                |
   +-----------------------------------------------+--------------------------------+
   | - Dell PowerEdge R510 server                  | Compute cluster capable server |
   | - 2 x 1TB drives                              |                                |
   +-----------------------------------------------+--------------------------------+

..

.. todo::

   Get RAM and CPU configruation for Seamus (R510 server).

..

.. _rightsandlicenses:

Proprietary nature, acquirer's rights, and licensing
----------------------------------------------------

Some tests defined and anticipated under this plan involve use of
a licensed `Jira`_ ticketing system using the `Zephyr for Jira`_
plugin. These are primarily development-related tests that fall under
the levels `Unit`, `Integration`, and/or `Component Interface` test
levels, of type `Expected Value` and/or `Desk check` as defined
in Section :ref:`testlevels` and :ref:`testclasses`, respectively.

.. _Jira: https://www.atlassian.com/software/jira/
.. _Zephyr for Jira: https://marketplace.atlassian.com/plugins/com.thed.zephyr.je

The remainder of the tests will use open source products either acquired from
their original source, or produced by the DIMS team and delivered with the
final system. (See Section :ref:`license` for the license under which DIMS
software is being released.)

.. _controls:

Installation, testing, and control
----------------------------------

Deployment tests will start with a bare-metal server with a network
connection capable of routing to the internet. From there, the following
general high-level steps will be performed:

#. Operating system installation to the bare-metal server will be
   performed according to steps outlined in documentation. (This may
   be done using DHCP dynamically assigned addresses so as to minimize
   the number of manual steps required to install the base operating
   system.)

#. Network level configuration of the operating system will be performed
   by manually entering the required attributes (e.g., the way `Security
   Onion Setup Phase 1`_ is performed) into a software configuration database
   and/or configuration file.

#. The software configuration database and/or configuration file will be
   applied to the system, configuring all DIMS components for initial
   use.

#. Further manual steps will be necessary to provision initial user
   accounts in the portal and/or other DIMS system administration
   components.

#. The system will be put into a "test" mode to perform system
   tests to validate that all DIMS components are up and running
   and the system is functional. Initial data input tests may
   be performed at this point to validate that input and output
   functions are working.


.. _Security Onion Setup Phase 1: https://youtu.be/D6IibAfPPD4

.. _participatingorgs:

Participating organizations
---------------------------

Table :ref:`paticipanttable` lists participants, their roles and responsibilities,
related to testing.

.. _paticipanttable:

.. table:: Participants Roles

    +------------------------+------------------------------------------------------------+
    | Participants           | Roles and Responsibilities                                 |
    +========================+============================================================+
    | DIMS development team\ | Primary persons involved in testing DIMS components at     |
    |                      \ | all test levels. Most will be on-site at the specified     |
    |                        | test locations, while some will be remote.                 |
    +------------------------+------------------------------------------------------------+
    | PRISEM participants  \ | Involved in higher-level testing focused on user           |
    |                      \ | acceptance testing and bug identification, as their time   |
    |                        | and availability permit.                                   |
    +------------------------+------------------------------------------------------------+
    | Other stakeholders   \ | Involved in higher-level testing focused on user           |
    |                      \ | acceptance testing and bug identification, as their time   |
    |                        | and availability permit.                                   |
    +------------------------+------------------------------------------------------------+

..

.. _orientationplan:

Orientation plan
----------------

People involved with testing will be provided with guidance in the form
of user documentation, a copy of this test plan, and any specifics of
how to perform the specified tests. This may include providing them with
access to software described in :ref:`softwareitems`, or some other
form of checklist that will enable them to know the tests to be performed,
acceptance criteria, and a means of reporting test results.

.. _teststoperform:

Tests to be performed
---------------------

Specific tests of test classes `expected value testing` and `desk check
testing` (see Section :ref:`testclasses`) that are manual in nature, and are
expected to be performed by stakeholders for the purpose of acceptance testing,
will be documented and provided as part of orientation prior to testing.
