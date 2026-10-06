# Project rules

1. Email validation must reject addresses without a dot in the domain (for example "a@b"). Add a test for it.
2. Trim whitespace on text fields before validating. A whitespace-only required field must show an error.
3. Every input has a visible <label> linked with for/id. Every error message uses role="alert" and aria-describedby.
4. Every validation function has a test in test.html. Do not mark a task done until all tests pass.