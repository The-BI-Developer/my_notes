Batteries Included philosphy

unit test - unit of code e.g. function
integration test - units can work
functional test - specific function working

Testing helps with ci/cd

asset is for sanity checks, not production

1. unittest module

writing tests + test runner

* tests are methods in a class
* built-in assertion methods

to define a test function:def test_<give_some_name>

unittest.TestCase must be parameterised in class argument

import code to be tested in self.assertEqual (as an example)

====example====
import unittest

def m(x,y):
    return x*x

class mt(unittest.TestCase):
    def test_something(self):
        test_x = 5
        test_y = 10
        
        self.assertEqual(m(test_x,test_y), 50, "Should be 50") #provide a function with test values, expected value, print explanation

if __name__ == '__main__':
    unittest.main()
====example====

* put tests in test.py
* multiple test.py files in a "test" folder (applicable to larger projects)

$ python -m unittest test_module #wont need unittest.main() this way

NOTE: Check DOCUMENTATION FOR TestCase assertions









