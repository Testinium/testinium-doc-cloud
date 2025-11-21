# Testinium-Cloud 3.1.1 Release Notes

#### Release Date: 13.11.2025

#### New Features

* Fargate integration has been added to enable container creation independent of executor resource limits, improving scalability under heavy test loads.
* Quickrun support has been added for service tests, allowing selected service scenarios to run without modifying the main plan configuration.
* Private Device Pool support has been added for Appium 2 executions, enabling isolated testing on private mobile devices.
* An Appium 1 → Appium 2 upgrade flow and project cloning feature have been introduced to support safe migration and versioning.
* Project cards now display project type and framework information for faster project identification.
* Container logs are now visible to users, enabling easier debugging during test execution.\
  XML reports are saved per plan and project and made available to users for faster failure analysis.
* Status filtering on the Quickrun page has been updated with new execution statuses.\
  Search capability has been added to dropdown components to improve navigation in long lists.
* Environment icons have been added to the Active Test page for easier device identification.
* Device reservation information is now tracked for Cloud Plugin executions, ensuring consistent coordination with Testinium Cloud runs.
* Dynamic status selection has been added to the line and pie charts on Report Execution and Report pages.
* Email reports now include Stopped and Unexecuted statuses to improve reporting accuracy.
* Appium 2 notification emails now include environment information.
* Queue Time is now displayed on the Active Test page, increasing transparency for queued executions.
* Scenario execution reports are now preserved and displayed even after the scenario is deleted.

#### Bug Fixes

* Fixed an issue where Quickrun allowed runs to start without selecting a scenario or environment.
* Resolved a problem where newly created users sometimes did not receive a Git user.
* Fixed an issue preventing device selection when the device SDK version was higher than the minimum supported version.
* Resolved a bug where tests did not run the expected number of retry attempts after an Error.
* Fixed reporting errors in Appium 2 executions where step failures such as NoSuchElementException were incorrectly shown as Error instead of Failure.
* Resolved an issue where Cucumber service projects with a ‘+’ in the method name became stuck in Reporting.
* Fixed an issue where the Access Token was not displayed on the Profile page.
* Resolved an error occurring when multiple plans were selected for grouped execution.
* Fixed a bug where stopped tests occasionally remained in the Terminating status.
* Resolved an issue where video or screenshot recording failures (e.g., curl26) caused the entire test to fall into Error.
* Fixed an issue where Appium 2 tests failed to start when the application was already installed on the device.

