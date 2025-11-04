## Test-Driven Development Methodology

Test-Driven development follows the principle "write tests (and interface) first,
see them fail and then write the implementation piece by piece until the tests succeed!".

In this context, a full run-through of TDD should be executed for each feature, i.e. each 
functional unit of the project. Such a unit might be a set of changes to many files
that enables a specific feature or it could also be a new class - don't be overly
sensitive and apply TDD for every minor change, but a general rule of thumb is 
that one user request, i.e. one major step in an implementation plan
requires one iteration of TDD.

One iteration of TDD goes through the following cycle:
- analyze user request and determine test cases (without writing code at this stage), show proposal
to user and get feedback, continue only after approval
- if new code units (classes, functions, ...) are required for the implementations, write
interfaces and mocks next; show user and get feedback, continue only after approval
- once that is done, execute the tests first - you should not see any errors besides failing tests;
if there are errors, now is the time to fix those
- once you have a clean bill of failing tests, start the implementation and 
re-execute the tests from time to time. Ideally, you should see steady progress
in the number of successful tests
- continue debugging, fixing and modifying your implementation until all tests are green
and then get user approval and review before you declare this task to be finished

**Important rules**
THere are some CRUCIAL rules you have to obey:
- once the user has approved the test cases, _NEVER_ again modify them - this is CRUCIAL for
the success of the process! Every change to the test require user approval and intervention
after the ffirst two phases
- make sure to write many orthogonal test cases, so you cover lots of ground (semantic) when testing,
avoid overly detailed and repetitive tests
- don't make your test cases too simple, but rather anticipate (based on the specs)
typical use cases of the _whole system_ and base your test case design on them

**User Feedback**
As mentioned above, there are three steps after which you are _NOT_ allowed to
move on in the process without _explicit_ user approval:
- proposing the test cases in natural language, especially including edge caases;
- having written out the interface code (and/or) mocks as well as implemented the
testing code;
- and, lastly, before declaring the task done.

At this stage, you can interact with the uer to improve your (intermediate) results,
but have to get permission first to continue.

**Output**
After each phase of TDD, the output is:
- a _single_, very short document outlining what steps have been taken in the implementation and what alterations *e.g. from your interactions with tools/tests or user feedback were needed -> `summary.md`
- the code that is written
- the tests that were written
- a demonstrated GREEN run of all tests in the project (as to avoid breaking tests in another phase)

These should be inside a folder `phase_X` where X is the number of the current phase inside the folder of the current session. In doubt, ask.

Note that if the user requested that tests are skipped, you do NOT need to create a "verification" script!
