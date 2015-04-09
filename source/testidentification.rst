.. _testidentification:

Test identification
===================

.. todo::

    This section shall be divided into the following paragraphs to identify and
    describe each test to which this STP applies.

..

.. _generalinfo:

General information
-------------------

.. todo::

    This paragraph shall be divided into subparagraphs to present general
    information applicable to the overall testing to be performed.

..

.. _testlevels:

Test levels
~~~~~~~~~~~

DIMS components will be tested at four distinct levels.

#. Unit tests -- These are tests of individual software components at the program or
   library level. These tests are primarily written by those who are developing
   the software to validate the software elements at a low (e.g., library or
   discrete shell command) perform their functions properly, independent
   of any other components.

#. Integration tests -- These are tests that are intended to verify the interfaces
   between components against the software design. Defects between interfaces are
   identified by these tests before their impact is observe at the system level
   through random or systemic failures.

#. Component interface tests -- These are checks of how data is processed as
   it is entered into and output from the system. Expected output may be compared
   against a cryptographic hash of the actual output to determine when actual
   output is malformed or otherwise deviates from expectations. Other interface
   tests (e.g., web application graphicial user interface input/output) may
   be tested manually through visual inspection by a test user.

#. System tests -- Also known as `end-to-end` tests, these are tests to
   determine if the overall system meets it requirements for general data
   processing and function. All system components produce test results that are
   complied into a single system test report that can be compared to detect
   differences between system tests, or to identify specific components that
   may have failed somewhere within the larger complex system.

.. _testclasses:

Test classes
~~~~~~~~~~~~~

We will employ one or more of the following classes of tests to DIMS
components:

* Expected value testing: values from the expected classes of the input
  domain will be used to test nominal performance

* Simulated data: simulated data for nominal and extreme geophysical
  conditions will be used to support error detection, recovery and reporting

* Erroneous input: sample values known to be erroneous will be used to test
  error detection, recovery and reporting

* Stress testing: maximum capacity of the input domain, including concurrent
  execution of multiple processes will be used to test external interfaces,
  error handling and size and execution time

* Timing testing: wall clock time, CPU time and I/O time will be recorded

* Desk check testing: both code and output will be manually inspected and
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

.. testprogression:

Test progression
~~~~~~~~~~~~~~~~

.. todo::

   In cases of progressive or cumulative tests, this paragraph shall explain
   the planned sequence or progression of tests.

..

.. _recordinganalysis:

Data recording, reduction, and analysis
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

.. todo::

   This paragraph shall identify and describe the data recording, reduction,
   and analysis procedures to be used during and after the tests identified in
   this STP. These procedures shall include, as applicable, manual, automatic,
   and semi-automatic techniques for recording test results, manipulating the
   raw results into a form suitable for evaluation, and retaining the results
   of data reduction and analysis.

..

.. _plannedtests:

Planned tests
-------------

.. todo::

   This paragraph shall be divided into the following subparagraphs to describe
   the total scope of the planned testing.

..

.. _bdscsci:

Backend Data Stores CSCI - (BDS)
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

The following sections describe the scope of formal testing for the Back End
Data Stores (BDS) CSCI.


.. _bdslevels:

Test Levels
^^^^^^^^^^^

.. _bdsclasses:

Test Classes
^^^^^^^^^^^^

.. _bdsconditions:

General Test Conditions
^^^^^^^^^^^^^^^^^^^^^^^

The following subparagraphs identify and describe the planned groups of tests.

.. todo::

   These paragraphs shall identify a test by project unique identifier and shall
   provide the information specified below for the test. Reference may be made
   as needed to the general information in 4.1.

   + Test objective
   + Test level
   + Test type or class
   + Qualification method(s) as specified in the requirements specification
   + Identifier of the CSCI requirements and, if applicable, software system
     requirements addressed by this test. (Alternatively, this information may be
     provided in Section 6.)
   + Special requirements (for example, 48 hours of continuous facility time, weapon
     simulation, extent of test, use of a special input or database)
   + Type of data to be recorded
   + Type of data recording/reduction/analysis to be employed
   + Assumptions and constraints, such as anticipated limitations on the test
     due to system or test conditions--timing, interfaces, equipment,
     personnel, database, etc.  Safety, security, and privacy considerations
     associated with the test

..


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
levels described in :ref:`testlevels`. The following paragraphs describe the
development and FQT test levels as they apply to the Dashboard Web Application.

.. _dwaunit:

Unit tests
""""""""""

Unit tests are performed during development and are written for the DWA Server
and DWA Client components of the CSCI. At a minimum, these tests are run
by developers and must pass before any code pushes to the Dashboard Web Application
repository. The continuous integration (CI) system will then run the tests
when new code is pushed to the repository. A failing test run on
the CI server requires a fix by developers before additional code
can be pushed. The CI server will maintain test run
results.

.. _dwaintegration:

Integration tests
"""""""""""""""""

Integration tests, performed during development, detect interface defects
within the Dashboard Web Application. DWA Client tests verify the DWA Client 
HTTP/HTTPS and socket interfaces. DWA Server tests verify the
Dashboard Web Application Server REST API, HTTP/HTTPS, Messaging,
and Socket interfaces. 

These tests are written and performed using automated test methods 
appropriate for Javascript client and server (Node.js) applications. 
The tests are run by the CI server when code is pushed
to the Dashboard Web Application repository to ensure new features do not
cause regression problems within the web application. The CI server will
maintain test run results.

.. _dwacomponent:

Component interface tests
"""""""""""""""""""""""""

Component inteface tests for the Dashboard Web Application will test the
DWA Client User Interface (UI). They are described in this document as part
of the FQT suite of tests.

.. _dwasystem:

System tests
""""""""""""

Test of the Dashboard Web Application at the system level will include
(1) End-to-end acceptance testing, performed by testers using the DWA Client UI, 
and (2) Automated tests to verify operation and availability of the CSCI at 
system startup and at defined intervals. They are described in this 
document as part of the FQT suite of tests.

.. _dwaclasses:

Test Classes
^^^^^^^^^^^^

The following classes of tests, described in :ref:`testclasses` will be 
peformed during formal qualification testing of the Dashboard Web Application CSCI:

* Expected value testing
* Simulated data
* Erroneous input
* Desk check testing

.. _dwaconditions:

General Test Conditions
^^^^^^^^^^^^^^^^^^^^^^^

The following subparagraphs identify and describe the planned collections of FQT tests.
Test personnel should have access to the Firefox web browser, VPN access, a
properly configured DIMS shell environment for testing.

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
   #. Special requirements: Access to the DIMS JIRA tool
   #. Type of data to be recorded: Tester, Execution date, Status (Pass/Fail)

.. _dwaacceptance:

Acceptance Tests
""""""""""""""""

This collection of tests are run by a Tester via the User Interface to
exercise the Dashboard Web Application and verify its functionality satisfies
requirements in user stories. Acceptance tests will be entered, managed, executed, 
and reported via JIRA. The test descriptions, steps, 
test data, expected results for each step,
and actual results will be included in the Test Report.

    #. Test levels: System
    #. Test type or class: Expected value, simulated data, erroneous input, desk check
    #. Qualification method: Test
    #. Special requirements: Access to the DIMS JIRA tool
    #. Type of data to be recorded: Tester, Execution date, Status (Pass/Fail) 

.. _dwaoperational:

Operational Tests
"""""""""""""""""

Tests in the Operational collection are automated tests that run when the CSCI is
started and at proscribed intervals during operation. These tests will report 
results via a log fanout and are used to verify system operation and availability.

    #. Test levels: System
    #. Test type or class: Timing, desk check
    #. Qualification method: Test
    #. Type of data to be recorded: Component ID, Wall clock time, other data TBD. 


.. _diutcsci:

Data Integration and User Tools CSCI - (DIUT)
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

The following sections describe the scope of formal testing for the Data
Integration and User Tools (DIUT) CSCI.

.. todo::

    .. warning::

       The :ref:`tupelo-testing` section needs to be merged into the DIUT CSCI
       component, restructured to fit consistently with the other related
       sub-sections. Look at :ref:`dwacsci` and the JHU ``dppoc_stp.pdf`` file
       for examples of the level of detail desired.

    ..

..

.. _diutlevels:

Test Levels
^^^^^^^^^^^

.. _diutclasses:

Test Classes
^^^^^^^^^^^^

.. _diutconditions:

General Test Conditions
^^^^^^^^^^^^^^^^^^^^^^^

The following subparagraphs identify and describe the planned groups of tests.

.. todo::

   These paragraphs shall identify a test by project unique identifier and shall
   provide the information specified below for the test. Reference may be made
   as needed to the general information in 4.1.

   + Test objective
   + Test level
   + Test type or class
   + Qualification method(s) as specified in the requirements specification
   + Identifier of the CSCI requirements and, if applicable, software system
     requirements addressed by this test. (Alternatively, this information may be
     provided in Section 6.)
   + Special requirements (for example, 48 hours of continuous facility time, weapon
     simulation, extent of test, use of a special input or database)
   + Type of data to be recorded
   + Type of data recording/reduction/analysis to be employed
   + Assumptions and constraints, such as anticipated limitations on the test
     due to system or test conditions--timing, interfaces, equipment,
     personnel, database, etc.  Safety, security, and privacy considerations
     associated with the test

..

.. _vliscsci:

Vertical/Lateral Information Sharing CSCI - (VLIS)
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

The following sections describe the scope of formal testing for the Vertical
and Lateral Information Sharing (VLIS) CSCI.

.. _vlislevels:

Test Levels
^^^^^^^^^^^

.. _vlisclasses:

Test Classes
^^^^^^^^^^^^

.. _vlisconditions:

General Test Conditions
^^^^^^^^^^^^^^^^^^^^^^^
The following subparagraphs identify and describe the planned groups of tests.

.. todo::

   These paragraphs shall identify a test by project unique identifier and shall
   provide the information specified below for the test. Reference may be made
   as needed to the general information in 4.1.

   + Test objective
   + Test level
   + Test type or class
   + Qualification method(s) as specified in the requirements specification
   + Identifier of the CSCI requirements and, if applicable, software system
     requirements addressed by this test. (Alternatively, this information may be
     provided in Section 6.)
   + Special requirements (for example, 48 hours of continuous facility time, weapon
     simulation, extent of test, use of a special input or database)
   + Type of data to be recorded
   + Type of data recording/reduction/analysis to be employed
   + Assumptions and constraints, such as anticipated limitations on the test
     due to system or test conditions--timing, interfaces, equipment,
     personnel, database, etc.  Safety, security, and privacy considerations
     associated with the test

..


