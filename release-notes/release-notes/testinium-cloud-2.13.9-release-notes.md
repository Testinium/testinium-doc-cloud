# Testinium-Cloud 2.13.9 Release Notes

#### **Release Date: 08.07.2025**

#### **New Features**

* Automatic pop-up closing has been implemented for mobile devices to prevent test interruptions (iOS 18 devices excluded).
* Rich text support has been added to the Announcement tab to enable more descriptive and visually enhanced communications.
* In random executions, scenarios in the waiting stage are now distributed to plan-assigned environments earlier for optimized device allocation.
* Methods causing ASCII errors can now be previewed during scenario creation to help users detect invalid method names before submission.
* A loading indicator has been added to table components during page transitions to improve user feedback and overall UX.

#### **Bug Fixes**

* Fixed an issue where error messages were not updated correctly in failed test retry executions.
* Resolved an error occurring when adding a large number of devices to a plan.
* Fixed a problem where Cucumber service projects remained in the “running” state due to missing runner classes.
* Corrected an issue where plugins not assigned to the user were still visible when a company plugin was added from the admin panel.
* Fixed the incorrect 1-second runtime display in service test executions.
* Resolved an issue where select boxes were automatically marked after performing a search on Plan and Scenarios pages.
* Fixed redundant requests and unnecessary data reloads during page transitions on the Scenarios page.
* Corrected the issue where the Account Information tab incorrectly displayed “There isn’t any information” despite existing data.
* Disabled the Stop button on the Active Plans page until a record is selected.
* Fixed an issue with the Running filter on the Plan page.
