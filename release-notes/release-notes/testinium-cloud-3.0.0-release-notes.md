# Testinium-Cloud 3.0.0 Release Notes

#### Release Date: 08.08.2025

#### New Features

* Added new end-to-end scenario execution statuses: Processing, Reporting, Terminating, Stopped, Unexecuted.
* Implemented environment and IPA/APK validation in plans to prevent misconfigured mobile test executions.
* Added dynamic status selection for the “End of Each Execution” notification type and warnings for duplicate notification entries.
* Enabled notifications to be activated or deactivated without manually removing email addresses.
* Added reporting support for Failed Test Retry Count so users can view retry attempts and errors separately.
* Simplified email content for the “Beginning of Each Execution” notification type for improved readability.
* Added pagination to the Active Tests and Active Plans dashboard sections for easier navigation in large executions.

#### Bug Fixes

* Unified data retrieval on the Dashboard to ensure consistency between card values and Latest Plan Run results.
* Fixed an issue occurring during TestRail suite selection.
