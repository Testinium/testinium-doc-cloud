# Testinium-Cloud 2.13.4 Release Notes

#### Release Date: 02.07.2024

#### New Features

* Gauge report details for service tests can now be viewed on scenario’s reports. 27.05.2024 hot fix
* Data loading time on the Automated Test - Operation Report page has been improved. Pagination structure has been updated.
* An endpoint has been created for plans and projects on the Scheduled Report page. The loading time of information on the Scheduled Report page has been improved.
* The template test projects in the Create From Template option for Selenium project selection on the Project Create page have been updated.
* The generated test code for the Java option on the Automated Test-Test Code Generator page has been updated.
* Search information has been added to the filter page service to display the number of results when searching on the Plan and Scenario pages.
* Different filters and search functionality have been enabled to work on the Scenario and Project listing pages.
* Files without ipa/apk extensions cannot be dragged and dropped for upload on the Automated Test page. 27.05.2024 hot fix
* The tab is displayed responsively in the Running Plans filter on the Plan listing page. The data on the listing page can also be displayed on running plans page.
* The Slack option is not displayed on the Schedule & Notification page if the Slack plugin is not defined for the user. 27.05.2024 hot fix
* An information message has been added to the Automated Test - Operation Reports page. 27.05.2024 hot fix
* An information message has been added to the Set system parameters field on the Plan and Scenarios pages. 27.05.2024 hot fix
* Information message has been added for mandatory fields on the Project, Scenario, and Scenario Group pages.
* Users with the Role Company Admin role can now view the Return to your own company button in assigned companies.
* The Contact us redirection link has been updated in the relevant fields within the product. 27.05.2024 hot fix
* An endpoint has been created to return a list of users by company for displaying statistical data on a user-based basis.
* A new endpoint has been created to return information on all companies that have the Livetesting plugin.
* A new 404 page has been created for unreachable pages.

#### Bug Fixes

* Fixed the bug where executions were not created in Xray integration.
* Fixed the error that occurred in accounts with the Xray plugin on the Plan Edit - Advanced Settings tab.
* Fixed the error that occurred on the Xray integration Scenario Create and Edit page in the Xray tag field.
* Resolved the error in the Plan Edit - Advanced Settings tab where the test plan to be mapped could not be found.
* Fixed the "You don't have slack plugin!" error that occurred on the Plan Edit-Schedule & Notifications tab.
* Fixed the error where Slack selection could not be added from the Notification Type field in Slack integration.
* Fixed the bug where notifications could not be sent to the selected channel in Slack integration.
* Fixed the bug where the update user and update date information in the filter on the Plan page were not being updated.
* Fixed the bug where the public report link from the Automated Test - Operation Reports page could not be accessed on browser.
* Fixed the bug where the public report link created for service tests was different from the report displayed on the report page. 09.05.2024 hot fix
* Fixed the bug where both the error message and the pop-up were appeared at the same time when encountering a Git repository error during project creation.
* Fixed the error that caused the framework tab to open when the Create button was clicked on the Project Create page when creating a new project.
* Fixed the bug where data entered in the Set System Parameters table on the Create New Scenario page was not being added.
* Fixed the bug where name and surname information did not update on the Dashboard page when changed in the Account Information - Users page. 27.05.2024 hot fix
* When creating a new account, the name and surname fields for the created user could not be filled in, the user name was made to be displayed responsively. 27.05.2024 hot fix
* The company search button on the Dashboard page was made to be displayed responsively when searching. 27.05.2024 hot fix
* The cards on the Project - Summary page were made to be displayed responsively. 09.05.2024 hot fix
* The Plan name on the Plan listing page was made to be displayed responsively. 09.05.2024 hot fix
* The Html Report page was made to be displayed responsively.
* The Take Screenshot, Screen resolution and Record video settings on the Automated test page were made to be displayed responsively.
* Fixed the error encountered when trying to view user details by clicking on the Users card on the Dashboard.
