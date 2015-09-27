# Test cases

Tests are defined in tests.json.  

The format of the tests.json file is an array of objects, where each object defines
a test, as follows:

- name - the name of the test. This is also used as the basis of the name of the
  JSON file with the expected results. E.g. the expected results for "test01" are
  in *test01-expected.json*.
- description
- tree - the tree to use as input. Note that a given tree can be used in more than
  one test.
- sizing - one of:
    - default - no sizing option is given to the tree layout object, meaning that
      it will default to size([1, 1]).
    - size - use size([x_size, y_size]) to define a fixed size for the
      entire resultant drawing.
    - node-size-fixed - use nodeSize([x_size, y_size]) to define a fixed size
      for all nodes
    - node-size-function - use the nodeSize(function) to specify a function that
      defines the (variable) node size. These tests will only be run against
      flextree. The function gets the node's size from its x_size and y_size
      attributes.
- gap - how the delta between nodes is defined
    - default - uses the default separation function
    - "separation-1" - constant separation function that always returns 1.


Here's some random information about the origins of some of the tests:

* tree-a - tree-e - are from random trees generated by the code
* tree-f - is a representation of a problem I was having with my implementation of
  "flextree". It works here.
* tree-g & tree-h - from Figure 6 of "Drawing Non-layered Tidy Trees in Linear Time".
  before-7.json is from the figure, and before-8.json is its mirror image,
  illustrating that the algorithm satisfies aesthetic 5.
* tree-i - a simple tree with fixed-sized nodes.

* tree-j - very simple tree to illustrate the difference betwee tree and flextree
* tree-k, tree-l, tree-m - more flextree test cases
* tree-n - from the "flare" database
