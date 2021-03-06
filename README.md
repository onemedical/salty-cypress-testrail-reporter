# TestRail Reporter for Cypress
Publishes [Cypress](https://www.cypress.io/) runs on TestRail.

Forked from the original package [salty-cypress-testrail-reporter](https://github.com/skekauoha/salty-cypress-testrail-reporter) by [Spencer Kekauoha](https://github.com/skekauoha)


## Install

```shell
$  npm install git+ssh://git@github.com:onemedical/cypress-testrail-reporter.git --save-dev
```

## Usage

Add reporter to your `cypress.json`:

```javascript
...
{
  "reporter": "cypress-testrail-reporter",
  "reporterOptions": {
    "domain": "yourdomain.testrail.com",
    "username": "username",
    "password": "password",
    "projectId": idNumber,
    "runId": testRunNumber,
  }
}
```

Your Cypress tests should include the ID of your TestRail test case. Make sure your test case IDs are distinct from your test titles:

```javascript
// Good:
it("C123 C124 Can authenticate a valid user", ...
it("Can authenticate a valid user C321", ...

// Bad:
it("C123Can authenticate a valid user", ...
it("Can authenticate a valid userC123", ...
```

## Reporter Options

**domain**: _string_ domain name of your TestRail instance (e.g. for a hosted instance _instance.testrail.com_).

**username**: _string_ email of the user under which the test run will be created.

**password**: _string_ password or the API key for the aforementioned user.

**projectId**: _number_ project with which the tests are associated.

**runId**: _number_ (optional: only necessary if createTestRun is set to true) a specific test run id number.


# Functionality Update 05/28/2019
- Updates the existing test run by pushing tbe test results from the automated test run execution.
- Does not require test suite id, only test run id is required
- TODO: figure out the way of publishing the test results in the project based on multiple test suites

## TestRail Settings

To increase security, the TestRail team suggests using an API key instead of a password. You can see how to generate an API key [here](http://docs.gurock.com/testrail-api2/accessing#username_and_api_key).

If you maintain your own TestRail instance on your own server, it is recommended to [enable HTTPS for your TestRail installation](http://docs.gurock.com/testrail-admin/admin-securing#using_https).

For TestRail hosted accounts maintained by [Gurock](http://www.gurock.com/), all accounts will automatically use HTTPS.

You can read the whole TestRail documentation [here](http://docs.gurock.com/).

## Author

Author: Yulduz Ibragimova - [github](https://github.com/yulduz-om)

## License

This project is licensed under the [MIT license](/LICENSE.md).

## Acknowledgments

* [Milutin Savovic](https://github.com/mickosav), author of the [cypress-testrail-reporter](https://github.com/Vivify-Ideas/cypress-testrail-reporter) repository the forked repository was cloned from (see below)
* [Spencer Kekauoha](https://github.com/skekauoha), owner of the [salty-cypress-testrail-reporter](https://github.com/skekauoha/salty-cypress-testrail-reporter) repository that was forked.
