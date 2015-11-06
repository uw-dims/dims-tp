.. _testidentification:

Test identification
===================

.. _generalinfo:

General information
-------------------

Tests described in this section trace back to the
:ref:`dimssr:dimssystemrequirements` document, Section
:ref:`dimssr:requirements`, as described in Section
:ref:`requirementstraceability`.

.. todo::

    .. note::

        For sections that provide traceback to requirements, use intersphinx
        linking to reference the requirements and/or user stories from the
        appropriate sub-section(s) of :ref:`dimssr:requirements`, like this:

        .. code-block:: yaml

            #. SR reference: :ref:`dimssr:attributestorage`, :ref:`dimssr:bdsuserstory1`

        ..

        Which renders like this:

        #. SR reference: :ref:`dimssr:attributestorage`, :ref:`dimssr:bdsuserstory1`

   ..

..

.. _testlevels:

Test levels
~~~~~~~~~~~

DIMS components will be tested at four distinct levels.

#. **Unit tests**: These are tests of individual software components at the program or
   library level. These tests are primarily written by those who are developing
   the software to validate the software elements at a low (e.g., library or
   discrete shell command) perform their functions properly, independent
   of any other components.

#. **Integration tests**: These are tests that are intended to verify the interfaces
   between components against the software design. Defects between interfaces are
   identified by these tests before their impact is observe at the system level
   through random or systemic failures.

#. **Component interface tests**: These are checks of how data is processed as
   it is entered into and output from the system. Expected output may be compared
   against a cryptographic hash of the actual output to determine when actual
   output is malformed or otherwise deviates from expectations. Other interface
   tests (e.g., web application graphical user interface input/output) may
   be tested manually through visual inspection by a test user.

#. **System tests**: Also known as `end-to-end` tests, these are tests to
   determine if the overall system meets it requirements for general data
   processing and function. All system components produce test results that are
   complied into a single system test report that can be compared to detect
   differences between system tests, or to identify specific components that
   may have failed somewhere within the larger complex system.

The first two levels of tests are performed on a continuous basis during
development. The final two levels pertain to the :term:`FQT`
described in this document.

.. _testclasses:

Test classes
~~~~~~~~~~~~~

We will employ one or more of the following classes of tests to DIMS
components:

#. **Expected value**: values from the expected classes of the input
   domain will be used to test nominal performance

#. **Simulated data**: simulated data for nominal and extreme geophysical
   conditions will be used to support error detection, recovery and reporting

#. **Erroneous input**: sample values known to be erroneous will be used to test
   error detection, recovery and reporting

#. **Stress**: maximum capacity of the input domain, including concurrent
   execution of multiple processes will be used to test external interfaces,
   error handling and size and execution time

#. **Timing**: wall clock time, CPU time and I/O time will be recorded

#. **Desk check**: both code and output will be manually inspected and
   analyzed


.. _testconditions:

General test conditions
-----------------------

.. todo::

   This paragraph shall describe conditions that apply to all of the tests or
   to a group of tests. For example: "Each test shall include nominal, maximum,
   and minimum values;" "each test of type x shall use live data;" "execution
   size and time shall be measured for each CSCI." Included shall be a
   statement of the extent of testing to be performed and rationale for the
   extent selected. The extent of testing shall be expressed as a percentage of
   some well defined total quantity, such as the number of samples of discrete
   operating conditions or values, or other sampling approach. Also included
   shall be the approach to be followed for retesting/regression testing.

..

.. _recordinganalysis:

Data recording, reduction, and analysis
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Test results from each test will be stored and indexed so as to be retrievable
and post-processed for two primary reasons:

#. To be able to compare `TestA` to `TestB` and determine the difference in
   results (e.g., to identify regression errors, site-specific differences that
   were not anticipated during development, or uncover latent bugs related to
   services that are not managed properly and may not come up after a
   crash or other failure condition.

#. To be able to produce reStructuredText format files that can be inserted
   into a directory hierarchy for the Test Report document that can then
   be rendered using Sphinx to produce a deliverable HTML and/or PDF version.

This will allow developers to test code releases before they are pushed to
"production" deployments, and for involved stakeholders doing independent field
testing to generate test reports that can be sent back to the DIMS development
team for debugging and code fixes.


.. _plannedtests:

Planned tests
-------------

.. _bdscsci:

Backend Data Stores CSCI - (BDS)
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Backend data stores include temporary and long-term storage of
event data, user attributes, user state, indicators and
observables, and other incident response related data produced
during use of the DIMS system.  The following sections describe the scope of
formal testing for the Backend Data Stores (BDS) CSCI.

.. _bdslevels:

Test Levels
^^^^^^^^^^^

General testing of the Backend Data Stores CSCI will take place at the
levels described in :ref:`testlevels`. Unit and integration levels apply to
development, and the remaining levels apply to :term:`FQT`.

* Unit tests
* Integration tests
* Component interface tests
* System tests

.. _bdsclasses:

Test Classes
^^^^^^^^^^^^

The following classes of tests, described in :ref:`testclasses` will be
performed during formal qualification testing of the Backend Data Stores CSCI:

* Expected value testing
* Simulated data
* Erroneous input
* Desk check testing

.. _bdsconditions:

General Test Conditions
^^^^^^^^^^^^^^^^^^^^^^^

The following sub-paragraphs identify and describe the planned collections of
:term:`FQT` tests.  Test personnel should have access to the Firefox web
browser, VPN access, a properly configured DIMS shell environment for testing.

.. _bdsacceptance:

Acceptance Tests
""""""""""""""""

This collection of tests are run by a Tester via the User Interface to
exercise the Backend Data Stores CSCI and verify its functionality satisfies
requirements in requirements and user stories. Acceptance tests will be
entered, managed, executed, and reported via JIRA. The test descriptions,
steps, test data, expected results for each step, and actual results will be
included in the Test Report.

#. Test levels: System
#. Test type or class: Expected value, simulated data, erroneous input, desk check
#. Qualification method: Test
#. SR reference: :ref:`dimssr:attributestorage`, :ref:`bdsuserstory1`,
   :ref:`dimssr:bdsuserstory2`,
#. Special requirements: Access to the DIMS JIRA tool
#. Type of data to be recorded: Tester, Execution date, Status (Pass/Fail)

.. _bdsoperational:

Operational Tests
"""""""""""""""""

Tests in the Operational collection are automated tests that run when the CSCI is
started and at proscribed intervals during operation. These tests will report
results via a log fanout and are used to verify system operation and availability.
(Some of the test capabilities in this category will also be used
for performance of the tests described in :ref:`statesmodes`.)

#. Test levels: System
#. Test type or class: Timing, desk check
#. Qualification method: Test
#. SR reference: :ref:`dimssr:bdsuserstory1`, :ref:`dimssr:bdsuserstory2`
#. Type of data to be recorded: Component ID, Wall clock time, other data TBD.


.. _dwacsci:

Dashboard Web Application CSCI - (DWA)
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

The Dashboard Web Application, also referred to as the DIMS Dashboard,
consists of web application server ("DWA Server") and
client ("DWA Client") components. The following sections
describe the scope of testing for the Dashboard Web Application CSCI.

.. _dwalevels:

Test Levels
^^^^^^^^^^^

General testing of the Dashboard Web Application CSCI will take place at the
levels described in :ref:`testlevels`. Unit and integration levels apply to
development, and the remaining levels apply to :term:`FQT`.

* Unit tests
* Integration tests
* Component interface tests
* System tests

.. _dwaclasses:

Test Classes
^^^^^^^^^^^^

The following classes of tests, described in :ref:`testclasses` will be
performed during formal qualification testing of the Dashboard Web Application CSCI:

* Expected value testing
* Simulated data
* Erroneous input
* Desk check testing

.. _dwaconditions:

General Test Conditions
^^^^^^^^^^^^^^^^^^^^^^^

The following sub-paragraphs identify and describe the planned collections of
:term:`FQT` tests.  Test personnel should have access to the Firefox web
browser, VPN access, a properly configured DIMS shell environment for testing.

.. _dwauserinterface:

User Interface Tests
""""""""""""""""""""

The purpose of this collection is to validate the functionality of
Dashboard Web Application User Interface (UI) elements.
UI tests will be entered, managed, executed, and reported via
JIRA. The test descriptions, steps,
test data, expected results for each step,
and actual results will be included in the Test Report.

#. Test levels: Component interface
#. Test type or class: Expected value, simulated data, erroneous input, desk check
#. Qualification method: Test
#. SR reference: :ref:`dimssr:dwauserstory7`
#. Special requirements: Access to the DIMS JIRA tool
#. Type of data to be recorded: Tester, Execution date, Status (Pass/Fail)

.. _dwaacceptance:

Acceptance Tests
""""""""""""""""

This collection of tests are run by a Tester via the User Interface to
exercise the Dashboard Web Application and verify its functionality satisfies
requirements in user stories. Acceptance tests will be entered, managed, executed,
and reported via JIRA. The test descriptions, steps, test data, expected results
for each step, and actual results will be included in the Test Report.

#. Test levels: System
#. Test type or class: Expected value, simulated data, erroneous input, desk check
#. Qualification method: Test
#. SR reference: :ref:`dimssr:dwauserstory1`, :ref:`dimssr:dwauserstory2`,
   :ref:`dimssr:dwauserstory3`, :ref:`dimssr:dwauserstory4`, :ref:`dimssr:dwauserstory5`,
   :ref:`dimssr:dwauserstory6`
#. Special requirements: Access to the DIMS JIRA tool
#. Type of data to be recorded: Tester, Execution date, Status (Pass/Fail)

.. _dwaoperational:

Operational Tests
"""""""""""""""""

Tests in the Operational collection are automated tests that run when the CSCI is
started and at proscribed intervals during operation. These tests will report
results via a log fanout and are used to verify system operation and availability.
(Some of the test capabilities in this category will also be used
for performance of the tests described in :ref:`statesmodes`.)

#. Test levels: System
#. Test type or class: Timing, desk check
#. Qualification method: Test
#. SR reference: :ref:`dimssr:dwauserstory8`
#. Type of data to be recorded: Component ID, Wall clock time, other data TBD.


.. _diutcsci:

Data Integration and User Tools CSCI - (DIUT)
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

The following sections describe the scope of formal testing for the Data
Integration and User Tools (DIUT) CSCI.

.. _diutlevels:

Test Levels
^^^^^^^^^^^

General testing of the Data Integration and User Tools CSCI will take
place at the levels described in :ref:`testlevels`. Unit and
integration levels apply to development, and the remaining levels
apply to :term:`FQT`.

* Unit tests
* Integration tests
* Component interface tests
* System tests

.. _diutclasses:

Test Classes
^^^^^^^^^^^^

The following classes of tests, described in :ref:`testclasses` will be
performed during formal qualification testing of the Data Integration
and User Tools CSCI:

* Expected value testing
* Simulated network failures testing
* Stress testing
* Timing testing

.. _diutconditions:

General Test Conditions
^^^^^^^^^^^^^^^^^^^^^^^

The following sub-paragraphs identify and describe the planned groups
of tests for the DIUT CSCI.

.. _duituserinterface:

Tupelo Whole Disk Initial Acquisition Test
""""""""""""""""""""""""""""""""""""""""""

This test relates to Tupelo, a whole disk acquisition and search tool
which is one component of the DIUT. The purpose of this test is to
ensure that the entire contents of a test disk of arbitrary size can
be uploaded to a Tupelo store component over a network.

#. Test Levels: integration, system
#. Test classes: expected value, timing, stress
#. Qualification Method: Demonstration, inspection
#. SR reference: :ref:`dimssr:diutuserstory6`
#. Type of Data Recorded: Copy of test disk content stored in Tupelo store.

Tupelo Whole Disk Subsequent Acquisition Test
"""""""""""""""""""""""""""""""""""""""""""""

This test also relates to Tupelo. The purpose of this test is to
ensure that the entire contents of a test disk of arbitrary size can
be uploaded to a Tupelo store component over a network.  That disk was
previously uploaded to the same store.  The upload time and filesystem
usage at the store site should be less than for an initial upload.

#. Test Levels: integration, system
#. Test classes: expected value, timing
#. Qualification Method: Demonstration, inspection
#. SR reference: :ref:`dimssr:diutuserstory6`
#. Type of Data Recorded: Test log showing smaller stored disk and
   reduced elapsed time for disk acquisition.


Tupelo Store Tools Test
"""""""""""""""""""""""

This test also relates to Tupelo. The purpose of this test is to
ensure that Tupelo store-processing tools can create so-called
'products' from previously uploaded disk images.  These products are
then to be stored in the same store as the images.

#. Test Levels: integration, system
#. Test classes: expected value, timing
#. Qualification Method: Demonstration, inspection
#. SR reference: :ref:`dimssr:diutuserstory6`
#. Type of Data Recorded: Products of store tools to exist as
   supplementary files in Tupelo store.


Tupelo Artifact Search Test
"""""""""""""""""""""""""""

This test also relates to Tupelo. The purpose of this test is to
ensure that a search request sent to a Tupelo store, via e.g. AMQP,
results in the correct response.  If the search input identifies an
artifact which should be found in the store, a positive result must be
communicated to the search invoker.  Similarly for a query which
should be not located.  The objective is to avoid false positives
and false negatives.


#. Test Levels: integration, system
#. Test classes: expected value, timing
#. Qualification Method: Demonstration, inspection
#. SR reference: :ref:`dimssr:diutuserstory6`
#. Type of Data Recorded: Log files generated when making test queries
   of the existence of various files to a Tupelo store.


Tupelo Sizing Test
""""""""""""""""""

This test also relates to Tupelo. The purpose of this test is to
stress the Tupelo software by inputting a large disk image, on the
order of 1 or even 2TB.

#. Test Levels: integration, system
#. Test classes: stress, timing
#. Qualification Method: Demonstration, inspection
#. SR reference: :ref:`dimssr:diutuserstory6`
#. Type of Data Recorded: Copy of test disk content stored in Tupelo store.


Tupelo Network Failure Test
"""""""""""""""""""""""""""

This test also relates to Tupelo. The purpose of this test is to
assert the correctness of the Tupelo store when a disk upload is
interrupted by both a client failure and a network failure.


#. Test Levels: integration, system
#. Test classes: expected state
#. Qualification Method: Demonstration, inspection
#. SR reference: :ref:`dimssr:diutuserstory6`
#. Type of Data Recorded: Summary of Tupelo store contents before and
   after a whole disk upload operation interrupted by a client or
   network failure.

Tupelo Boot Media Test 1
""""""""""""""""""""""""

This test also relates to Tupelo. The purpose of this test is to check
that a computer can be booted from a CD/USB containing a Linux Live CD
with integrated Tupelo software, and that the local hard drive(s) of
that computer can be uploaded to a remote Tupelo store over the network.

#. Test Levels: integration, system
#. Test classes: expected state
#. Qualification Method: Demonstration, inspection
#. SR reference: :ref:`dimssr:diutuserstory6`
#. Type of Data Recorded: Observed behavior during demonstration.
#. Special Requirements: Tupelo Boot CD

Tupelo Boot Media Test 2
""""""""""""""""""""""""

This test also relates to Tupelo. The purpose of this test is to check
that a computer can be booted from a CD/USB containing a Linux Live CD
with integrated Tupelo software, and that the local hard drive(s) of
that computer can be uploaded to a Tupelo store located on a locally
attached external hard drive.

#. Test Levels: integration, system
#. Test classes: expected state
#. Qualification Method: Demonstration, inspection
#. SR reference: :ref:`dimssr:diutuserstory6`
#. Type of Data Recorded: Disk contents of computer's own hard drive
   and external hard drive.
#. Special Requirements: Tupelo Boot CD and External Hard Drive and
   Cabling

.. _diutuserinterface:

User Interface Tests
""""""""""""""""""""

The purpose of this collection is to validate the functionality of
the Data Integration and User Tools capabilities related to
general incident response and/or incident tracking or investigative
activities.
These tests are related to tests described in :ref:`dwauserinterface` in the DWA CSCI section.
DIUT CSCI tests will be entered, managed, executed, and reported
via JIRA. The test descriptions, steps, test data, expected results for each
step, and actual results will be included in the Test Report.

#. Test levels: Component interface
#. Test type or class: Expected value, simulated data, erroneous input, desk check
#. Qualification method: Test
#. SR reference: :ref:`dimssr:diutuserstory2`, :ref:`dimssr:diutuserstory8`
#. Special requirements: Access to the DIMS JIRA tool
#. Type of data to be recorded: Tester, Execution date, Status (Pass/Fail)

.. _diutacceptance:

Acceptance Tests
""""""""""""""""

This collection of tests are run by a Tester via the User Interface to
exercise the Data Integration and User Tools capabilities
and verify its functionality satisfies
requirements in user stories.
These tests are related to tests described in :ref:`dwaacceptance` in the DWA CSCI section.
Acceptance tests will be entered, managed, executed,
and reported via JIRA. The test descriptions, steps, test data, expected results
for each step, and actual results will be included in the Test Report.

#. Test levels: System
#. Test type or class: Expected value, simulated data, erroneous input, desk check
#. Qualification method: Test
#. SR reference: :ref:`dimssr:incidenttracking`, :ref:`dimssr:knowledgeacquisition`,
   :ref:`dimssr:aggregatesummary`, :ref:`dimssr:diutuserstory1`,
   :ref:`dimssr:diutuserstory3`, :ref:`dimssr:diutuserstory4`, :ref:`dimssr:diutuserstory5`,
   :ref:`dimssr:diutuserstory7`
#. Special requirements: Access to the DIMS JIRA tool
#. Type of data to be recorded: Tester, Execution date, Status (Pass/Fail)

.. _diutoperational:

Operational Tests
"""""""""""""""""

Tests in the Operational collection are automated tests that run when the CSCI is
started and at proscribed intervals during operation. These tests will report
results via a log fanout and are used to verify system operation and availability.
(Some of the test capabilities in this category will also be used
for performance of the tests described in :ref:`statesmodes`.)

#. Test levels: System
#. Test type or class: Timing, desk check
#. Qualification method: Test
#. SR reference: :ref:`dimssr:aggregatesummary`, :ref:`dimssr:diutuserstory2`,
   :ref:`dimssr:diutuserstory4`, :ref:`dimssr:diutuserstory8`
#. Type of data to be recorded: Component ID, Wall clock time, other data TBD.


.. _vliscsci:

Vertical/Lateral Information Sharing CSCI - (VLIS)
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

The following sections describe the scope of formal testing for the Vertical
and Lateral Information Sharing (VLIS) CSCI.

.. _vlislevels:

Test Levels
^^^^^^^^^^^

General testing of the Vertical and Lateral Information Sharing CSCI will take
place at the levels described in :ref:`testlevels`. Unit and
integration levels apply to development, and the remaining levels
apply to FQT.

* Unit tests
* Component interface tests
* System tests

.. _vlisclasses:

Test Classes
^^^^^^^^^^^^

The following classes of tests, described in :ref:`testclasses` will be
performed during formal qualification testing of the Vertical and
Lateral Information Sharing CSCI:

* Expected value testing

.. _vlisconditions:

General Test Conditions
^^^^^^^^^^^^^^^^^^^^^^^
The following sub-paragraphs identify and describe the planned groups of tests.

Ingest of Indicators of Compromise via STIX Documents
"""""""""""""""""""""""""""""""""""""""""""""""""""""

This test relates to stix-java and Tupelo.  stix-java is a
DIMS-sourced Java library for manipulation of Mitre's STIX document
format.  STIX documents containing indicators-of-compromise (IOCs) in
the form of file hashes and file names shall be parsed.  The hashes
and names shall be submitted to the DIMS Tupelo component, and all the
stored disks searched for the IOCs.  Hit or miss results are then
collected.


#. Test Levels: component interface, system
#. Test classes: expected value
#. Qualification Method: Demonstration, inspection
#. SR reference: :ref:`dimssr:structuredinput`
#. Type of Data Recorded: Copy of search results, copy of input STIX
   documents, summary of Tupelo store state.

Authoring of Indicators of Compromise via STIX Documents
""""""""""""""""""""""""""""""""""""""""""""""""""""""""

This test relates to stix-java.  stix-java is a DIMS-sourced Java
library for manipulation of Mitre's STIX document format.  STIX
documents containing indicators-of-compromise (IOCs) in the form of
file hashes and file names shall be created.  The hashes and names
shall be auto-generated from output of CIF feeds, from Ops-Trust email
attachments and from Tupelo whole disk analysis results.

#. Test Levels: component interface, system
#. Test classes: expected value
#. Qualification Method: Demonstration, inspection
#. SR reference: :ref:`dimssr:structuredinput`
#. Type of Data Recorded: Copy of created STIX
   documents, summary of Tupelo store state, CIF feed results


.. _statesmodes:

States and Modes
~~~~~~~~~~~~~~~~

There are several states/modes that the DIMS system must support,
including a `test mode`, `debug mode`, and a `demonstration mode`.
The following section describes the scope of testing for these states/modes.

.. _statesmodesevels:

Test Levels
^^^^^^^^^^^

General testing of the required states/modes will take place at the
`System level` only, as described in :ref:`testlevels`.

.. _statesmodesclasses:

Test Classes
^^^^^^^^^^^^

The following classes of tests, described in :ref:`testclasses` will be
performed during formal qualification testing of states/modes.

* Desk check testing

.. _statesmodesconditions:

General Test Conditions
^^^^^^^^^^^^^^^^^^^^^^^

The following sub-paragraphs identify and describe the planned collections of
:term:`FQT` tests.  Test personnel should have access to the Firefox web
browser, VPN access, a properly configured DIMS shell environment for testing.

.. _statesmodestests:

States/Modes Tests
""""""""""""""""""

The purpose of this collection is to validate the functionality of
the defined states/modes.  These tests will be entered, managed, executed, and
reported via JIRA. The test descriptions, steps, test data, expected results
for each step, and actual results will be included in the Test Report.

#. Test levels: System level
#. Test type or class: Desk check
#. Qualification method: Test
#. SR reference: :ref:`dimssr:modetoggles`, :ref:`dimssr:testmode`,
   :ref:`dimssr:debugmode`, :ref:`dimssr:demomode`
#. Special requirements: Access to the DIMS JIRA tool
#. Type of data to be recorded: Tester, Execution date, Status (Pass/Fail)


.. _security:

Security and Privacy Tests
~~~~~~~~~~~~~~~~~~~~~~~~~~

There are several security controls related to user accounts, access keys, and
network access.  The following section describes the scope of testing for these
aspects of DIMS.

.. _securityevels:

Test Levels
^^^^^^^^^^^

General testing of the required security and privacy requirements will take
place at the `Component interface level` and `System level`, as described in
:ref:`testlevels`.

.. _securityclasses:

Test Classes
^^^^^^^^^^^^

The following classes of tests, described in :ref:`testclasses` will be
performed during formal qualification testing of states/modes.

* Expected value testing
* Erroneous input
* Desk check testing

.. _securityconditions:

General Test Conditions
^^^^^^^^^^^^^^^^^^^^^^^

The following sub-paragraphs identify and describe the planned collections of
:term:`FQT` tests.  Test personnel should have access to the Firefox web
browser, VPN access, a properly configured DIMS shell environment for some
testing, while other tests (e.g., port scanning) will be done from external
hosts without any proper account or credential data.

.. _securitytests:

Security Tests
""""""""""""""

The purpose of this collection is to validate the functionality of
the defined security and privacy requirements.  These tests will be entered,
managed, executed, and reported via JIRA. The test descriptions, steps, test
data, expected results for each step, and actual results will be included in
the Test Report.

#. Test levels: Component interface level, System level
#. Test type or class: Expected value, Erroneous Input, Desk check
#. Qualification method: Test
#. SR reference: :ref:`dimssr:networkaccesscontrols`,
   :ref:`dimssr:accountaccesscontrols`,
   :ref:`dimssr:secondfactorauth`, :ref:`dimssr:accountsuspension`,
   :ref:`dimssr:rekeying`
#. Special requirements: Access to the DIMS JIRA tool
#. Type of data to be recorded: Tester, Execution date, Status (Pass/Fail)

.. _securityoperational:

Operational Tests
"""""""""""""""""

Tests in the Operational collection are automated tests that run on-demand or
at proscribed intervals during normal operation. These tests will report
results via both the DWA CSCI components, and a log fanout and are used to
verify system operation and availability.  (Some of the test capabilities in
this category are closely related to tests described in
:ref:`diutoperational`.)

#. Test levels: System
#. Test type or class: Timing, desk check
#. Qualification method: Test
#. SR reference: :ref:`dimssr:diutuserstory2`, :ref:`dimssr:diutuserstory4`,
   :ref:`dimssr:diutuserstory5`
#. Type of data to be recorded: Component ID, Wall clock time, other data TBD.


.. note::

   An application penetration test of DIMS components, including the
   :ref:`dwacsci` and the ops-trust portal (part of :ref:`vliscsci` and
   desribed in :ref:`dimsocd:dimsoperationalconceptdescription`, Sections
   :ref:`dimsocd:opstrustportalnow` and :ref:`dimsocd:opstrustportalchanges`)
   is to be performed by a professional service company.

   This is a separate test from those described in this Test Plan,
   and the results will be reported in a separate document to be
   included in the final Test Report.

..
