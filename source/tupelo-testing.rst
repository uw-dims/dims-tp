.. _tupelo-testing:

Testing Tupelo
==============

Introduction
------------

Tupelo is a DIMS software component whose role is to manage the acquisition of
whole hard drive images to a centralised location, and later to answer
questions related to hard drive content.  A common question in this
arena might be "does any drive in the acquired set contain a file
with name *F*, or contain a file whose content hash is *C*.

Tupelo supports acquiring many drives at many points in time.  Thus
drive *D1* might be acquired at times *T1, T3, T5*, while drive
*D2* might be acquired at times *T2* and *T5*.  Once acquired, any
*Di,Ti* is never changed, it becomes read-only.

The test cases noted in this section relate to testing the correct
acquisition (upload) of drives over time, so that the contents of a
Tupelo store is as expected.  The tests also cover expected and actual
answers to questions such as "does the store contain an artifact named *X*?"


Site
----

::

   $ mvn site

..

Components to be tested
-----------------------

Tupelo is a Java codebase.  The source code is organized as multiple
Maven `modules
<http://books.sonatype.com/mvnex-book/reference/multimodule.html>`_
under a common root filesystem directory.  Adhering to accepted Maven
build practices, each Tupelo module builds a single *artifact*.  Most
artifacts in Tupelo are simply libraries of code to be used by larger
applications. In Java, such libraries are packaged as *.jar*
files. Source version control for the Tupelo codebase is via git.

There remain three artifacts which can be classed as applications.  One
is a Java web application and the other two are command line programs.
These three programs are deployable units of code and are the primary
targets for testing.  The programs are

1. Tupelo networked-accessible component called the ``Store``, also known
   as the Tupelo ``server``. The CSCI (Computer Software Component
   Item) identifier for this component shall be ``Tupelo-Server``.
   
2. Tupelo command-line program called the ``Shell``. The shell is the
   primary user interface for uploading local disk contents to a
   remote Tupelo server. The CSCI identifier for this component shall
   be ``Tupelo-Shell``.
   
3. Tupelo command-line programs using AMQP message bus to ask and answer
   questions related to Tupelo store content.  The CSCI identifier for
   this component shall be ``Tupelo-Query``.
   

.. note::

Want to classify the DIMS STIX tools as Tupelo components?  If no,
how/when are these tested?


Unit testing
------------

Each Tupelo Maven module contains various unit tests.  These tests
are geared towards verifying the correctness of each Java class or set
of tightly-coupled classes within a module.  No human interaction is
required for unit testing.

.. note::

Local test data for unit tests?  Can be large, several GB?  Separate
git repo for test data?

..

To perform the unit tests, it is assumed that the local tester has
access to the Tupelo source code (held in a git repository local to
DIMS) and the appropriate build and test tool environment.  This
environment is essentially just

1. a Java Development Kit version 1.7 or higher
   
2. the Maven project management tool, version 3.0.5 or higher



::

   $ cd /path/to/tupelo
   $
   $ mvn clean
   $
   $ mvn test -Ptester


Tupelo-Server CSCI
------------------


Test Levels
~~~~~~~~~~~

Formal testing of the Tupelo-Server CSCI will be accomplished at the:

* Unit test level 
  
* CSCI level
  
* CSCI to CSCI level

Test Classes
~~~~~~~~~~~~

Once web app running, can test 3 basic pieces of functionality:

1 Does tupelo server announce itself to amqp 'log monitor'?

2 Does tupelo server respond to http requests for various disk
acquistion functions.

3 Does tupelo server respond to amqp requests for file hash search
 queries.


Server Test 2:

In simplest form, use wget/curl to iterate through a few
'informational urls', e.g. 

server version string, 

disk space left,

store uuid.

Can do these with just

$ wget http://localhost:8888/tupelo/version

etc.


The above steps build, package and locally install into the user's
Maven repository (``~/.m2/repository) all of the Tupelo modules.

of all the 
   $ demo.tupelo -s http://192.168.1.50:8080/tupelo

..


Tupelo-Shell CSCI
-----------------

Tupelo-Query CSCI
-----------------



Integration testing
-------------------


Performance testing
-------------------


* how long does a first acquire take?
  
* how long does a digest step take?
  
* how long does a subsequent acquire take?

* how long does it take to produce the digest file of any acquired drive?
* how long does each store tool take : digest, bodyfile, etc?

  
* how much store disk is taken up by each acquire?
  
* for search: how long to answer yes/no?  Need secs per GB/TB stored?

.. eof

