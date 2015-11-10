.. _appendices:

Appendices
==========

.. _jiratestplanner:

Planning tests with JIRA
------------------------

This section describes how to plan a test cycle using JIRA.

We use a test cycle to plan and execute our tests. To view test cycles,
click Tests > Plan Test Cycle:

.. figure:: images/jira/plan_cycle1.png
    :alt: View test cycles
    :width: 100%

..

The list of cycles displays. We need a new cycle for the tests due on
11/15, so we'll create one. Click the Create New Cycle button to bring up
a dialog to create the cycle. Give it a name and description.

.. figure:: images/jira/create_cycle1.png
    :alt: View test cycles
    :width: 100%

..

The new test cycle displays in the list. You can see that it doesn't have any
tests yet.

.. figure:: images/jira/create_cycle2.png
    :alt: View test cycles
    :width: 100%

..

For the purposes of this documentation, we created another cycle called
Sample Test Cycle as well.

To create a new test, select Tests > Create a Test.

.. figure:: images/jira/create_issue1.png
    :alt: View test cycles
    :width: 100%

..

The Create Issue screen displays, with the issue type already set to Test.
Enter a summary for the test, and fill in choices in the testLevel, testClass, and
qualificationMethod pick boxes. These are described in this Test Plan. You should also
a the reference to the DIMS SR - these are referenced in Section 4 of this plan for each
group of planned tests. typeOfData describes where the output data will be when
you are done. You can add this later if you don't know it at this time.

.. todo::

    Will we have a dictionary of SR references to choose from? Can there be more
    than one entry for SR reference? (Right now the field is just a text field).
    Also need direction on how to format typeOfData. If path is in the dims-tr, how
    is it referenced? $GIT/dims-tr/path/to/file? Are there other types other than
    file?

..

The following figure shows the first part of the Create Issue dialog being filled
in:

.. figure:: images/jira/create_issue2.png
    :alt: View test cycles
    :width: 100%

..

Scrolling down, you describe the Environment and provide a Description of the test.
The environment entry should be short - we should probably come up with some standard
choices for this. If the test needs a local Vagrant VM to run, then the Test should
reference how that is created in the Prerequisites.

Prerequisites can be added in the Description field. We could also put them as a
separate test step - whichever works best. There isn't a dedicated field available
for them. When you initially create the test, you can just add
a short description and add prerequisites by editing the test.

.. figure:: images/jira/create_issue3.png
    :alt: View test cycles
    :width: 100%

..

Save the test. You can further fill out fields by editing the test. For example,
you can upload files needed to run the test. In this example, we are uploading a
file with test data and a script which will run a number of automated tests using
the test data file as input:

.. figure:: images/jira/upload_files.png
    :alt: View test cycles
    :width: 100%

..

If files aren't attached, the prerequisites should state where to get them.

Add the test to the desired test cycle. Select More Actions > Add to Test Cycle(s):

.. figure:: images/jira/add_to_test_cycle1.png
    :alt: View test cycles
    :width: 100%

..

Select the test cycle. In this example, we choose the Sample Test Cycle. You would
choose the 2015-100-15_test_report test cycle for actual tests.

.. figure:: images/jira/add_to_test_cycle2.png
    :alt: View test cycles
    :width: 100%

..

The test will now show up in the list of tests for that test cycle. The E button
on the right is the button to click when you are going to execute the test.

.. figure:: images/jira/add_to_test_cycle3.png
    :alt: View test cycles
    :width: 100%

..

To create more tests, you can do so from scratch, or you can clone an existing
test. Go to the existing test, and click Clone.


.. figure:: images/jira/clone_test1.png
    :alt: View test cycles
    :width: 100%

..

Enter a new summary for the new test. You can clone attachments if the same ones
are used for the new test.

.. figure:: images/jira/clone_test2.png
    :alt: View test cycles
    :width: 100%

..

Here is an updated Sample test 2. Prerequisite info has been added to the
description. The comment regarding "if test fails" isn't needed - that was put in
before we had the typeOfOutput field (will update this screenshot later);

Since this test is automated, we just have one step - to run the test script.
The Expected Result is given as how many tests should pass.

.. todo::

    Not sure the best way to do the automated tests in JIRA. In this method, if
    one out of the 12 tests fail, the failing test item isn't shown on the ticket.
    The test output will need to be inspected. (The failed portion could be noted
    in the comments during execution however - see below).

..

.. figure:: images/jira/sample_test_2_updated.png
    :alt: View test cycles
    :width: 100%

..

.. figure:: images/jira/execute_test1.png
    :alt: View test cycles
    :width: 100%

..

.. figure:: images/jira/execute_test2.png
    :alt: View test cycles
    :width: 100%

..

.. figure:: images/jira/failed_test1.png
    :alt: View test cycles
    :width: 100%

..

.. figure:: images/jira/new_test_execute1.png
    :alt: View test cycles
    :width: 100%

..

.. figure:: images/jira/new_test_execute1.png
    :alt: View test cycles
    :width: 100%

..

