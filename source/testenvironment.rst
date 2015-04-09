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

.. todo::

    This paragraph shall identify by name, number, and version, as applicable,
    the software items (e.g., operating systems, compilers, communications
    software, related applications software, databases, input files, code
    auditors, dynamic path analyzers, test drivers, preprocessors, test data
    generators, test control software, other special test software, post
    processors) necessary to perform the planned testing activities at the test
    site(s). This paragraph shall describe the purpose of each item, describe
    its media (tape, disk, etc.), identify those that are expected to be
    supplied by the site, and identify any classified processing or other
    security or privacy issues associated with the software items.

.. _swtable:

.. table:: Software Table

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
    | Other???               | ...                                                        |
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

.. table:: Hardware Table

    +------------------------+----------------------------------+
    | Hardware item          | Purpose                          |
    +========================+==================================+
    | Dell PowerEdge ???     | column 2                         |
    +------------------------+----------------------------------+
    | Switch...              | ...                              |
    +------------------------+----------------------------------+
    | Blah, blah...          | ...                              |
    +------------------------+----------------------------------+
    | Blah, blah...          | ...                              |
    +------------------------+----------------------------------+
    | Blah, blah...          | ...                              |
    +------------------------+----------------------------------+
    | Blah, blah...          | ...                              |
    +------------------------+----------------------------------+

..

.. _othermaterials:

Other materials
---------------

.. todo::

    This paragraph shall identify and describe any other materials needed for
    the testing at the test site(s). These materials may include manuals,
    software listings, media containing the software to be tested, media
    containing data to be used in the tests, sample listings of outputs, and
    other forms or instructions. This paragraph shall identify those items that
    are to be delivered to the site and those that are expected to be supplied
    by the site.  The description shall include the type, layout, and quantity
    of the materials, as applicable. This paragraph shall identify any
    classified processing or other security or privacy issues associated with
    the items.

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

.. todo::

    This paragraph shall identify the developer's plans for performing each of
    the following, possibly in conjunction with personnel at the test site(s):

    Acquiring or developing each element of the software test environment
    Installing and testing each item of the software test environment prior to
    its use Controlling and maintaining each item of the software test
    environment 3.x.6   Participating organizations.

    This paragraph shall identify the organizations that will participate in
    the testing at the test sites(s) and the roles and responsibilities of
    each.


.. _personnel:

Personnel
---------

.. todo::

    This paragraph shall identify the number, type, and skill level of
    personnel needed during the test period at the test site(s), the dates and
    times they will be needed, and any special needs, such as multishift
    operation and retention of key skills to ensure continuity and consistency
    in extensive test programs.


.. _orientationplan:

Orientation plan
----------------

.. todo::

    This paragraph shall describe any orientation and training to be given
    before and during the testing. This information shall be related to the
    personnel needs given in 3.x.7. This training may include user instruction,
    operator instruction, maintenance and control group instruction, and
    orientation briefings to staff personnel. If extensive training is
    anticipated, a separate plan may be developed and referenced here.


.. _teststoperform:

Tests to be performed
---------------------

.. todo::

   This paragraph shall identify, by referencing section 4, the tests to be
   performed at the test site(s).

..

