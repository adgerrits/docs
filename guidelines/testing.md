# Guidelines for testing

Contents:

- Tag 'test'
- Test-scope

## Tag 'test'

Each Ansible role should have a tag for running a test, that can be run after installing the product.
To run the test for a specific role the tag `test` is used.

The `tasks/main.yml` of each role contains a task that only runs when `-t test` is used when running the role:
```
- name: Test
  import_tasks: test/tasks/test.yml
  tags: [ never, test ]
```

## Test-scope

What is tested?

* *Do a smoketest*

  The main purpose of the tests provided in the role is to check whether the product is installed
  correctly by doing a 'smoke test'.

* *Do not try to do deep functional tests*

  We expect functional tests in the project of the product itself.

* *Add a test for an open issue*

  Create a test when you know there is an issue (e.g. a bug that has not been fixed) that can result in incorrect
working of the product.

* *Add test for customization of the product*

  When a customization of a product is done, make sure specials are tested.

* *Try to keep the time consumed by the test low*

  The test should not take lots of time. Waiting for it to finish should not be a problem :-)

* *Use tag `system-check` for longer running tests*

  For tests that are useful in some cases, but not always, because they take too long, use the tag `system-check`

* *Clean up after testing*

  After creating objects during a test, also make sure the objects are cleaned up after

* *Naming temporary test objects*

  When creating temporary objects in a test, use a name that is recognizable; e.g. start with `cno-test-<role>-`

* *Clean code*

  Tests are also written as conform the [Clean Code book](http://cleancoder.com/products).

