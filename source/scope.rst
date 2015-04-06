.. _scope:

Scope
=====

.. todo::

   This section shall be divided into the following paragraphs.

..

.. _identification:

Identification
--------------

.. todo::

   This paragraph shall contain a full identification of the system and the
   software to which this document applies, including, as applicable,
   identification number(s), title(s), abbreviation(s), version number(s), and
   release number(s).

..

This Software System Test Plan (version |version|) documents the objectives,
approach, and scope/limitations of the testing and evaluation of the
Distributed Incident Management System (DIMS).  It describes the logistics for
executing the plan, including test environment needs, high level schedule, and
resource mapping.  It also identifies technical and schedule risks and
mitigation plans.  This plan will be utilized by the project team to properly
scope, manage, and comprehend test efforts.  This test plan is specific to
software, as defined within the statement of work.

.. _systemoverview:

System overview
---------------

.. todo:: 

   This paragraph shall briefly state the purpose of the system and the
   software to which this document applies. It shall describe the general
   nature of the system and software; summarize the history of system
   development, operation, and maintenance; identify the project sponsor,
   acquirer, user, developer, and support agencies; identify current and
   planned operating sites; and list other relevant documents.

..

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
the existing functionality of their current system

.. todo::

   The previous paragraph appears to trail off. Complete this.

..

.. _swsystemteststrategy:

Software System Test Strategy (General)
---------------------------------------

The software system test strategy we will employ is compromised of two
high-level sets of tests.  The first set of test will be developed as the
system is being designed using the Agile coding methodology.  Development and
pre-release testing will be performed during "sprints" (cycles of development
anticipated to be on 2 week time frames). These tests are centered on
development and take place within the project team.  The project team will
extract user stories from the use cases and in turn create epics derived from
the user stories.  Tests will be written for the user stories and determine the
necessary development.  This is essentially a test-driven approach that pushes
development from one sprint to the next.  The other set of tests will be
performed with interaction from the stakeholders and will entail an environment
in which the stakeholders will, at determinate intervals, access the system and
execute one or more user stories.  This environment, set up specifically for
stakeholders, will enable them to interact with the system at their discretion
and direct their feedback to the project team about the functionality delivered
within their environment. 

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

.. _relationshiptootherplans:

Relationship to other plans
---------------------------

.. todo::

    This paragraph shall describe the relationship, if any, of the STP to
    related project management plans.

