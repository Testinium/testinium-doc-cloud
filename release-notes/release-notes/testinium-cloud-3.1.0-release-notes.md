# Testinium-Cloud 3.1.0 Release Notes

#### Release Date: 04.09.2025

#### New Features

* Appium 2 support has been added for all mobile project types (Java, Gauge, Cucumber), enabling users to run tests on the latest Appium framework.
* Success rate calculation for Failed test retry count-based executions has been updated so that the final retry attempt determines the plan’s success rate.
* A success rate pie chart has been added to the Plan Report Details page.\
  Scenario reports can now be accessed directly from the Active Test list page.
* Character validation has been implemented for plan and scenario parameters to prevent invalid input.
* Runtime formatting in notification emails has been updated from milliseconds to hours/minutes/seconds for improved readability.
* “Stopped” and “Unexecuted” statuses have been added to pie charts on the Dashboard and Report pages for more comprehensive status visibility.

#### Bug Fixes

* Fixed a bug that prevented the automatic confirmation of the trust prompt during app installation.
* Resolved an error related to third-party authentication during the login process.
* Resolved a bug that triggered a new package creation when editing a private package.
