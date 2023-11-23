# flags

| **Description**               | **Syntax**                                      |
| ----------------------------- | ----------------------------------------------- |
| Increase Vebosity             | \-v                                             |
| Show full verbosity           | \-vv                                            |
| Pattern Matching              | \-k "expression"                                |
| Traceback style               | \-tb=(no/long/short)                        |
| Shows order of operaations of tests & fixtures                              | \ --setup-show                                                |
| View where fixtures are. Fixtures in conftest are located at the bottom of output.               | \--fixtures -v)                        |
| View what fixtures are used by each test and where the fixtures are defined.               | \--fixtures-per-test)                        |


# commands

| **Test Type**                 | **Syntax**                                      |
| ----------------------------- | ----------------------------------------------- |
| Single Test                   | `pytest test_module.py::test_function`          |
| All Tests in Module/Filename  | `pytest test_module.py`                         |
| All Tests in Multiple Files   | `pytest file_name.py file_name.py`              |
|                               |                                                 |
| Single Test Method            | `pytest test_module.py::TestClass::test_method` |
| All Tests in Class            | `pytest test_module.py::TestClass`              |
|                               |                                                 |
| All Tests in Dir              | `pytest test_path`                              |
|                               |                                                 |


# Fixtures

Fixture functions are a mechanism pytest provides to allow the seperation of "_getting ready for_" and "_cleaning up after_" cpde from test_functions.

Fixtures can be defined with the following syntax: `@pytest.fixture()'

Pytest have different failure status depending on where the assert failure lies:
- FAIL: test code -> assert failure
- ERROR: fixture -> assert failure.

NOTE: We never call fixture functions directly. This is the point of pytest and the decorator idiot!

Using `pytest --fixtures -v` allows us to view all of the available fixtures that our test can use.
Fixtures defined in a `conftest.py` are found at the bottom of the output.

<img width="1287" alt="image" src="https://github.com/parminder-thindal-moj/cheat_sheets/assets/93984622/82e3ee43-6d50-44d5-929a-75ee4925df1b">

If you supply a directory, pytest will list the fixtures available to the tests in that directory.
<img width="943" alt="image" src="https://github.com/parminder-thindal-moj/cheat_sheets/assets/93984622/0597f578-1772-4de4-b302-c4f9f461f645">


If you supply a filename, pytest will include those defined the test modules as well.

Pytest also includes the first line of the docstring from the fixture (if defined), alongside the file and line number of where the fixture is defined.
It will also include a path if it's not in your current directory.

## Scopes:

Scope is defined with the fixture. The scope is set at the definition of a fixture, and not at the place where it's called.

Run down of the following scopes available:

|  **Description**              | **Scopes**                                      |
| ----------------------------- | ----------------------------------------------- |
| Run one per test function. Setup portion is run before each test using the fixture. The teardown portion is run after each test using the fixture. Default when no scope defined.      | _scope="function"_      |
| Run once per test class - regardless of how many test methods are in the class.    | _scope="class"_      |
| Run once per module - regardless of how many test functions of methods or other fixtures in the module use it | _scope="module"_      |
| Run once per package, or test directory, regardless of how many test functions or methods or other fixtures in the package use it. | _scope="package"_      |
| Run oncer per session. All test methods and functions using a fixture of session scope share one setup and teardown call. | _scope="session"_      |

The test functions that use a fixture don't control how often the fixture is setup or town down. With a fixture defined in a test module, the session and package scopes
act just like module scope. Need to put these.

Fixtuees can only depend on other fixtures of their same scope or wider. 

Function scope fixtures can only depend on other function scope fixtures (the default) and so on.

A function-scope fixture can also depend on class-, module-, and session-scope fixtures, but you can't go in the reverse order.

Tests should not rely on run order.

## Conftest.py

You can put fixtures into individual test files, but to share fixtures among multiple test files, you need to use a `conftest.py` file, 
either in the same directory as the test file that's using it, or in a parent directory.

Considered as a local plugin by pyrest as a "local plugin" and can contain hook functions and fixtures.

`conftest.py` is a python module, but it should not imported by the test files. `conftest.py` file gets read by pytest automatically, so you don't have to import conftest anywhere!
