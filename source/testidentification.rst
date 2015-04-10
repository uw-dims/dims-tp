.. _testidentification:

Test identification
===================

.. _generalinfo:

General information
-------------------

Tests described in this section trace back to the DIMS System Requirements document
Section :ref:`dimssr:requirements`.

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
   tests (e.g., web application graphical user interface input/output) may
   be tested manually through visual inspection by a test user.

#. System tests -- Also known as `end-to-end` tests, these are tests to
   determine if the overall system meets it requirements for general data
   processing and function. All system components produce test results that are
   complied into a single system test report that can be compared to detect
   differences between system tests, or to identify specific components that
   may have failed somewhere within the larger complex system.

The first two levels of tests are performed on a continuous basis during
development. The final two levels pertain to the final
qualification testing (FQT) described in this document.

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

   This paragraph shall be divided into the following sub-paragraphs to describe
   the total scope of the planned testing.

..

.. _bdscsci:

Backend Data Stores CSCI - (BDS)
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

The following sections describe the scope of formal testing for the Backend
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

The following sub-paragraphs identify and describe the planned groups of tests.

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
levels described in :ref:`testlevels`. Unit and integration levels apply to
development, and the remaining levels apply to FQT.

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

The following sub-paragraphs identify and describe the planned collections of FQT tests.
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

General testing of the Data Integration and User Tools CSCI will take
place at the levels described in :ref:`testlevels`. Unit and
integration levels apply to development, and the remaining levels
apply to FQT.

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




Tupelo Whole Disk Subsequent Acquisition Test
"""""""""""""""""""""""""""""""""""""""""""""

This test also relates to Tupelo. The purpose of this test is to
ensure that the entire contents of a test disk of arbitrary size can
be uploaded to a Tupelo store component over a network.  That disk was
previously uploaded to the same store.  The upload time and filesystem
usage at the store site should be less than for an initial upload.



Tupelo Store Tools Test
"""""""""""""""""""""""

This test also relates to Tupelo. The purpose of this test is to
ensure that Tupelo store-processing tools can create so-called
'products' from previously uploaded disk images.  These products are
then to be stored in the same store as the images.



Tupelo Search Test
""""""""""""""""""

This test also relates to Tupelo. The purpose of this test is to
ensure that a search request coming into a Tupelo store, via
e.g. AMQP, results in the correct response.  If the search input
identifies an artifact which should be found in the store, a positive
result must be communicated to the search invoker.  Similarly for a
query which should be not located.  The objective is to thus avoid
false positives and false negatives.

Tupelo Sizing Test
""""""""""""""""""

This test also relates to Tupelo. The purpose of this test is to
stress the Tupelo software by inputting a large disk image, on the
order of 1 or even 2TB.


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
The following sub-paragraphs identify and describe the planned groups of tests.

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


