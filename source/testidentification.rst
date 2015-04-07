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

.. _itemstobetested_1:

(Item(s) to be tested)
~~~~~~~~~~~~~~~~~~~~~~

.. todo::

    This paragraph shall identify a CSCI, subsystem, system, or other entity by
    name and project unique identifier, and shall be divided into the following
    subparagraphs to describe the testing planned for the item(s). (Note: the
    "tests" in this plan are collections of test cases. There is no intent to
    describe each test case in this document.)


.. _projectid_1:

(Project-unique identifier of a test)
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. todo::

   This paragraph shall identify a test by project unique identifier and shall
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

.. _projectid_2:

(Project-unique identifier of a test)
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. todo::

   This paragraph shall identify a test by project unique identifier and shall
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

DIMS Web Application CSCI - (Unique Identifier)
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

The DIMS Web Application, also referred to as the DIMS Dashboard or simply 
"Web Application", consists of
web application server ("Server") and client ("Client") components. The following sections 
describe the scope of testing for the DIMS Web Application CSCI.

Test Levels
^^^^^^^^^^^

Testing of the Web Application CSCI will take place at the following levels:

* Unit tests - Unit tests will be written as appropriate for the Server 
  and Client components of the CSCI. At a minimum, these tests will be run
  by developers and must pass before any code pushes to the Web Application
  repository. The continuous integration (CI) system will then run the tests 
  when new code is pushed to the repository. A failing test run on
  the CI server requires a fix by developers before additional code 
  can be pushed. The CI server will maintain test run
  results. 

  Since Unit tests are part of the development process and are
  written and performed in a continuous fashion, they are not included in 
  this document as planned tests. However, overall results as reported by
  the CI server will be included in the Test Report.

* Integration tests - These will test the Server and Client components as a group
  and verify their interfaces. They will consist primarily of:

  + Server API tests - These will test the Server APIs accessed by the Client
  + Client functional tests - These will verify the Client user interface
    operates as designed. These will be run manually by a tester.

* Component interface tests - These tests will consist of a set of User tests,
  performed manually by a tester against the Client user interface, which will
  verify that data requested by the Client matches the expected output.

* System tests - the Web Application will be tested as part of the system 
  end-to-end testing.

.. note::

    Need more info on what our end-to-end testing will look like and how the
    web application can participate in that. 

..

Test Classes
^^^^^^^^^^^^

The following classes of tests will be peformed during formal testing of the
Web Application CSCI:

* Expected value testing
* Simulated data
* Erroneous input
* Desk check testing

General Test Conditions
^^^^^^^^^^^^^^^^^^^^^^^

The following subparagraphs identify and describe the planned groups of tests.
Test personnel should have access to the Firefox web browser, VPN access, a 
properly configured DIMS shell environment for testing.

User Interface Functional Tests
"""""""""""""""""""""""""""""""

The purpose of this test group is to ensure the Client User Interface operates as required.
This group will consist of a series of tests which exercise User Interface
functions and are performed by a human tester. These tests will be entered and managed in
JIRA. The test descriptions, steps, test data, expected results for each step,
and test results will be reported in the Test Report.

   + Test levels: Integration, Component Interface, System
   + Test type or class: Expected value, simulated data, erroneous input, desk check
   + Qualification method: Demonstration, inspection
   + Special requirements: Access to the DIMS JIRA tool
   + Type of data to be recorded: Tester, Execution date, Status (Pass/Fail)




