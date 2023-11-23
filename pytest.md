### pytest Commands

| **Description**               | **Syntax**                                      |
| ----------------------------- | ----------------------------------------------- |
| Increase Vebosity             | \-v                                             |
| Show full verbosity           | \-vv                                            |
| Pattern Matching              | \-k "expression"                                |
| Traceback style               | \-tb={long | short | no}                        |
|                               |                                                 |


Pytest - test commands

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
