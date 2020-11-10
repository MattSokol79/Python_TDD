# TDD - Test Driven Development
## Type of testing
- Unit testing
- TDD

**Python has several modules that we can use to
test our code**
- Pytest
- Unittest

**Why TDD??**

![](tdd.png)

- TDD helps us minimise the risk of failure
before sending a unfinished/buggy product to 
production

**Steps** 
- We will create a file to write our tests
- We will run the tests, they will all **FAIL**
- We will create a file to write our code
- We will refactor the code so tests **PASS**

**Naming convention for test files and methods**
- file name simple_calc
- test_simple_calc

**Install the testing frameworks**
```python
pip install pytest
# Unittest is already installed in python
```

### Test File
- First create the test class with the code shown
below and then create your actual code to test
```python
# This file will have our tests

# Importing the required modules
from simple_calc import Simple_Calc
import unittest
import pytest

# Let's create a class to write our tests

# unittest.TestCase works with unittest framework as a parent class
class Calctest(unittest.TestCase):


# Creating an object of class
    calc = Simple_Calc()

# IMPORTANT - we MUST use test word in our functions so python interpreter
# knows what we are testing
# Command shows if tests pass --------> python -m pytest <----------------
# Command to show details of tests--------> python -m pytest -v <--------------

    def test_add(self):
        self.assertEqual(self.calc.add(4, 2), 6) # Bool
        # This is what we are asking python to test for us
        # We are asking python to test/check if 2 + 4 = 6, if True, pass the test if False, fail

    def test_subtract(self):
        self.assertEqual(self.calc.subtract(4, 2), 2) # Bool
        # Test if 4 - 2 = 2, if True, pass test, if False, fail the test

    def test_multiply(self):
        self.assertEqual(self.calc.multiply(4, 2), 8) # Bool
        # Test if 4 * 2 = 8, if True, pass, else, False and fail test

    def test_divide(self):
        self.assertEqual(self.calc.divide(4, 2), 2) # Bool
        # Test if 4 / 2 = 2, if True, pass the test, else False, fail test
```

### Actual code file
```python
# This file will have our functional code to pass the tests

class Simple_Calc:

    def add(self, value1, value2):
        return value1 + value2

    def subtract(self, value1, value2):
        return value1 - value2

    def multiply(self, value1, value2):
        return value1 * value2

    def divide(self, value1, value2):
        return value1 / value2
```