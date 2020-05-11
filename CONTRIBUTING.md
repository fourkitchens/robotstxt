Contributing
============

Thank you for considering contributing to Robotstxt.  All contributions are welcome, encouraged, and valued.  Contributions no matter how small will receive recognition on drupal.org via the credit system.

CONTENTS OF THIS FILE
---------------------

 * Contact
 * Roadmap
 * Setup
 * Testing
 * Releases

Contact
-------

Are you looking to contact a maintainer or file an issue?  All management of issues is handled on drupal.org.

https://www.drupal.org/project/issues/robotstxt

Roadmap
-------

The current plan for the project looks something like:

  1. Semantic versioning
  2. Addressing any open issues
  3. Increasing test coverage and types of tests

Setup
-----

Currently you should be testing with the latest stable release of Drupal core.  Any additional versions of Drupal that should be tested against will be configured by the maintainer and run by the Drupal testbot.

It is recommended to use dorgflow for working on issues [joachim-n/dorgflow](https://github.com/joachim-n/dorgflow).  Once dorgflow is installed you can use the dorgflow command within the git tracked module by:

```
# NOTE: Check out the major version you want to contribute to then run:
dorgflow https://www.drupal.org/project/robotstxt/issues/{insert-issue-number}
```

Don't have an issue number?  Create and issue and let us know what you are working on.

Testing
-------

### PHPUnit
Running PHPUnit tests can be done with a command similar to the following depending upon your local environment:

```
php vendor/bin/phpunit -c web/core/phpunit.xml.dist web/modules/contrib/robotstxt/tests/src/Functional/RobotsTxtBasicTest.php
```

It is recommended you setup a fresh copy of Drupal core for testing this module as that is how your patches will be tested.  An example Drupal core project recommended file that works with testing this project against Drupal 8.8.x has been included in the examples directory.

### Reviewing
In order for a patch to be considered for committing it:

  1. MUST pass existing tests or existing tests MUST be modified
  2.

NOTE: The key words “MUST”, “MUST NOT”, “REQUIRED”, “SHALL”, “SHALL NOT”, “SHOULD”, “SHOULD NOT”, “RECOMMENDED”, “MAY”, and “OPTIONAL” in the documentation above are to be interpreted as described in [RFC 2119](https://tools.ietf.org/html/rfc2119).

Patches
-------

It is recommended to use dorgflow to create patches for you so that you can upload them to drupal.org.  You can use the following dorgflow command to create a patch:

```
# NOTE: Yes this doesn't have any arguments
dorgflow
```

Committing
----------

When an issue on drupal.org has been marked as RTBC and verified as good by a maintainer.  The following command can be used to commit the patch:

@todo
This was the previous workflow but may be broken:

```
dorgflow https://www.drupal.org/project/robotstxt/issues/{insert-issue-number}
dorgflow apply
dorgflow cleanup
# Alternatively, remove all inactive branches with
dorgflow purge
```

@todo
https://semantic-release.gitbook.io/semantic-release/#commit-message-format

Figure out how this will work with new commit message structure ?

fix(some-bug): Issue# {issue-#} by {user(s)}: {description}
feat(some-feature): Issue# {issue-#} by {user(s)}: {description}
perf(some-bug): Issue# {issue-#} by {user(s)}: {description}

BREAKING CHANGE: {breaking-change-description}

### Valid Commit:

https://github.com/angular/angular.js/blob/master/DEVELOPERS.md#type

Release management
------------------

This project uses semantic versioning managed by npm packages.

Guidance: https://semver.org/
