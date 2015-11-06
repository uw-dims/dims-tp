.. _scope:

Scope
=====

.. _identification:

Identification
--------------

This Software System Test Plan (release |release|) documents the objectives,
approach, and scope/limitations of the testing and evaluation of the
Distributed Incident Management System (DIMS).  It describes the logistics for
executing the plan, including test environment needs, high level schedule, and
resource mapping.  It also identifies technical and schedule risks and
mitigation plans.  This plan will be utilized by the project team to properly
scope, manage, and comprehend test efforts.  This test plan is specific to
software, as defined within the statement of work.

This Test Plan describes the Formal Qualification Test (FQT) activities and the
environment in which those activities will take place for the DIMS deployed
system. DIMS is composed of the following Computer Software Configuration Items
(CSCIs):

.. _capabilityrequirements:

CSCI capability requirements
----------------------------

DIMS is funded by the Department of Homeland Security under contract HSHQDC-
13-C-B0013.

The DIMS system is divided into the following high-level CSCI sets,
per the acquisition contract.

================================ ========= =============
CSCI                             Label     Contract Item
================================ ========= =============
Backend data stores              BDS       C.3.1.1
Dashboard web application        DWA       C.3.1.1
Data Integration and User Tools  DIUT      C.3.1.2
Vertical/Lateral Info. Sharing   VLIS      C.3.1.3
================================ ========= =============

Reference :ref:`dimssr:dimssystemrequirements` establishes the
DIMS software requirements. Reference :ref:`dimsocd:dimsoperationalconceptdescription`
describes the operational concept (and open source design concept) for DIMS.
Reference :ref:`dimsad:dimsarchitecturedesign` sets forward the architectural
design.  Unit testing and integration testing will be performed during
development at the University of Washington. This document primarily addresses
the :term:`FQT` activities that take place when deploying the DIMS software.

.. _systemoverview:

System overview
---------------

The primary mission objectives for the DIMS system are operational in nature,
focused on facilitating the exchange of operational intelligence and applying
this intelligence to more efficiently respond and recover from cyber
compromise. The secondary mission objectives are to create a framework in which
tools to support the primary mission objectives can more quickly and easily be
integrated and brought to bear against advancing techniques on the attacker
side of the equation.

The DIMS project is intended to take this semi-automated sharing of structured
threat information, building on the success of the Public Regional Information
Security Event Monitoring (PRISEM) project and leveraging an existing community
of operational security professionals known as Ops- Trust, and scale it to the
next level. The intent of this software project is to allow for near real-time
sharing of critical alerts and structured threat information that will allow
each contributing party to receive information, alerts and data, analyze the
data, and respond appropriately and in a timely manner through one
user-friendly web application, DIMS.

Working with the use cases defined by MITRE and PRISEM users, building the
features necessary to simplify structured information sharing, and
operationalizing these within these existing communities, will allow DIMS to
fill existing gaps in capabilities and support existing missions that are
slowed down today by many complicated, manual processes.

The changes to existing systems consists of seamless integration of the three
current systems into a single web application that enables each system to
contribute to the data warehouse of information concerning threats, alerts,
attacks and suspect or compromised user terminals within the infrastructure.
Additionally, the integrated systems will be able to share and retrieve data,
visually observe alerts through color coded visual indicators, while retaining
the existing functionality of the current system.

.. _swsystemteststrategy:

Software System Test Strategy (General)
---------------------------------------

The software system test strategy we will employ is compromises two
high-level sets of tests.

The first set of test will be developed as the system is being designed using
the Agile coding methodology.  Development and pre-release testing will be
performed during "sprints" (cycles of development anticipated to be on 2 week
time frames). These tests are centered on development and take place within the
project team.  The project team will extract user stories from the use cases
and in turn create epics derived from the user stories.  Tests will be written
for the user stories and determine the necessary development.  This is
essentially a test-driven approach that pushes development from one sprint to
the next.

The other set of tests will be performed with interaction from the
stakeholders and will entail an environment in which the stakeholders will, at
determinate intervals, access the system and execute one or more user stories.
This environment, set up specifically for stakeholders, will enable them to
interact with the system at their discretion and direct their feedback to the
project team about the functionality delivered within their environment.

Delivery of software for testing will be conducted in the following manner:

+ Software for the project will be developed using the Agile Methodology and
  will therefore be delivered incrementally, based on completed functionality
  for each Sprint.

+ Each Sprint cycle is anticipated to be two to four (2-4) weeks.

+ A final feature complete build will be delivered at the completion of development.

+ Testing efforts will be structured to test the delivered functionality of
  each Sprint's delivered software module(s).

+ Feature complete builds will be tested as integrated modules.

+ Iterations of testing will be conducted as builds are delivered to address
  bug fixes as well as delivered features or functionality.



.. _documentoverview:

Document overview
-----------------

The purpose of this document is to establish the requirements for the testing
of the Distributed Incident Management System (DIMS). The structure of this
document and the strategy for testing has been adapted principally from
MIL-STD-498 (see Section :ref:`referenceddocs`). It contains the following
information:

+ Section :ref:`referenceddocs` lists related documents.

+ Section :ref:`testenvironment` specifies the test environment that will be
  used in testing DIMS CSCIs. It includes a description of the hardware,
  software and personnel resources needed for installation, testing and
  control.

+ Section :ref:`testidentification` provides general information about
  test levels and test classes, general test conditions, and planned
  tests.

+ Section :ref:`requirementstraceability` describes traceability of tests back
  to requirements.

+ Section :ref:`notes` provides an alphabetical listing of acronyms and
  abbreviations used in this document.

