.. _testschedules:

Test schedules
==============

.. todo::

   This section shall contain or reference the schedules for conducting the
   tests identified in this plan. It shall include:

   A listing or chart depicting the sites at which the testing will be
   scheduled and the time frames during which the testing will be conducted

   A schedule for each test site depicting the activities and events listed
   below, as applicable, in chronological order with supporting narrative as
   necessary: On site test period and periods assigned to major portions of the
   testing Pretest on site period needed for setting up the software test
   environment and other equipment, system debugging, orientation, and
   familiarization Collection of database/data file values, input values, and
   other operational data needed for the testing Conducting the tests,
   including planned retesting Preparation, review, and approval of the
   Software Test Report (STR)

..

To date, two sets of tests at all levels and classes as defined in Section
:ref:`testidentification`. Each of these tests took a significant effort from
all team members in order to perform and report on the results.

Due to the amount of effort required, full tests to the same extent as
previous tests will only be performed when absolutely necessary and within
available staff resources.

Because of the amount of effort required, more automated tests in the
**component**, **interface**, and **system** levels (primarily in the
form of **expected_value** class tests) that can be integrated into
the system provisioning and Ansible configuration processes to assist
with regression testing and acceptance testing of bugfix and feature
branches prior to making new releases.  The use of the `TAP`_-compiant
`Bats`_ program, and `Robot Framework`_ (see Section :ref:`swtable`),
will eventually allow an automated test and report generation flow that could
support more frequent tesing with less staff time required to perform the
testing.

.. _Robot Framework: http://robotframework.org/
.. _Bats: https://github.com/sstephenson/bats#bats-bash-automated-testing-system
.. _TAP: http://testanything.org

