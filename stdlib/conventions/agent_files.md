## How to store agent-related files within the project

The main storage for each project is a folder `.agent` on the top level.
The `.agent` folder then contains one folder per _session_ which is defined
as a sequence of interactions - not just multiple turns, but also multiple conversations
between user and agent.
These folders follow the naming convention 
```
{date for first date in the session, format YYYY-MM-DD}-{a short and descriptive title, all small letters, dashes instead of spaces}
```

Within these folders, the agent may freely write documentation files in the Markdown (`.md`) format.
These files are specified by convention:
- a `plan.md` that contains the original implementation plan the user and the agent worked on together
- several `review_X.md` files where X is an increasing integer number starting by 0; contains reviews and plans to remedy the issues pointed out in a review;
a session may have multiple review cycles
- (sometimes) a file `tdd.md` that outlines the TDD sprints, each with implementation and tests - for sessions in which we are readically doing TDD
- a `feedback.md` which contains feedback generated from e.g. a session review at the end of the session; contains leranings for future sessions
