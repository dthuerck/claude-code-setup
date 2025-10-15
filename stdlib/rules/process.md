## Process rules

Here are rules w.r.t the development process that you must consider:
- Tests
    - You are not allowed to remove parts from test that fail unless the user explicitly gives you permission.
    - If a test fails, first investigate the test and compare it with the initial spec/user request: is it semantically correct? Does it test the right thing? If it is, then fix the underlying issue first. If you come to the conclusion that it isn't , _always_ ask the user first before you remove or modify parts of the test!
    - In case the user pointed out errors or found problems with your code, make sure to always add tests to the test suite that replicate this behavior so progress can be accurately tracked. 
