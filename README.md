# codeclimate-test-reporter

[![Code Climate](https://codeclimate.com/github/codeclimate/javascript-test-reporter/badges/gpa.svg)](https://codeclimate.com/github/codeclimate/javascript-test-reporter)
[![Test Coverage](https://codeclimate.com/github/codeclimate/javascript-test-reporter/badges/coverage.svg)](https://codeclimate.com/github/codeclimate/javascript-test-reporter)

Supplies a script which accepts lcov data over standard input, formats the coverage data and sends it to Code Climate.

Code Climate - [https://codeclimate.com](https://codeclimate.com)

# Important FYIs

Across the many different testing frameworks, setups, and environments, there are lots of variables at play. Before setting up test coverage, it's important to understand what we do and do not currently support:

* **Default branch only:** We only support test coverage for your [default branch](http://docs.codeclimate.com/article/151-glossary-default-branch). Be sure to check out this branch before running your tests.
* **Single payload:** We currently only support a single test coverage payload per commit. If you run your tests in multiple steps, or via parallel tests, Code Climate will only process the first payload that we receive. If you are using a CI, be sure to check if you are running your tests in a parallel mode.

  **Note:** There is one exception to this rule. We've specifically built an integration with [Solano Labs](https://www.solanolabs.com/) to support parallel tests.

  **Note:** If you've configured Code Climate to analyze multiple languages in the same repository (e.g., Ruby and JavaScript), we can nonetheless only process test coverage information for one of these languages. We'll process the first payload that we receive.
* **Invalid File Paths:** By default, our test reporters expect your application to exist at the root of your repository. If this is not the case, the file paths in your test coverage payload will not match the file paths that Code Climate expects.

## Installation

This npm package requires having a user (but not necessarily a paid account) on Code Climate, so if you don't have one the
first step is to create an account at: [https://codeclimate.com](https://codeclimate.com). Then:

1. Generate coverage data in [lcov](http://ltp.sourceforge.net/coverage/lcov/geninfo.1.php) format

      Lcov data can be generated by a number of JavaScript code coverage tools, including [Istanbul](http://gotwarlost.github.io/istanbul).

1. Install codeclimate's NPM package

          $ npm install -g codeclimate-test-reporter

1. Specifying your repo token as an environment variable, send lcov coverage data to the codeclimate npm script.

      For example, if your coverage data resides in a "lcov.info" file:

          CODECLIMATE_REPO_TOKEN=ABCD11110000000 codeclimate-test-reporter < lcov.info

The `CODECLIMATE_REPO_TOKEN` value is provided after you add your repo to your
Code Climate account by clicking on "Setup Test Coverage" on the right hand side of your feed.

Please contact hello@codeclimate.com if you need any assistance setting this up.

## Troubleshooting

If you're having trouble setting up or working with our test coverage feature, [see our detailed help doc](http://docs.codeclimate.com/article/220-help-im-having-trouble-with-test-coverage), which covers the most common issues encountered.

## Contributions

Patches, bug fixes, feature requests, and pull requests are welcome on the
GitHub page for this project: [https://github.com/codeclimate/javascript-test-reporter](https://github.com/codeclimate/javascript-test-reporter)

## Copyright

See LICENSE.txt
