# Testinium-Cloud 2.13.5 Release Notes

#### Release Date: 28.08.2024

#### New Features

* The 'waiting' status was added to the Dashboard, Reports, and Plans pages, so users can see the scenario status from when the plan starts until it begins running.
* Users can now download the execution reports from the Operation Report tab on the Automated Test page to their local device.
* The Excel file downloaded from the Plans page now includes dynamic information. Users can see the filter details they selected on the screen in the downloaded Excel file.
* A message was added to the Properties page when the Git address doesn’t have a master branch. If the master branch isn’t used, the main branch is set. If neither exists, the user is informed.
* The Test Result button on the Scheduled & Notification page, which allows selecting the test result notification type, now works dynamically with the selected test execution status.
* An example folder path was added to the Plan Advance Setting page in Web plans to inform users about the File Upload to Node setting.
* Assignee, Reporter, Labels, Test Environments fields were updated on the Plan Edit page for Xray integration. Loading was added to the page, improving its loading speed.
* A message was updated to inform users about the error details on the Plan - Schedule & Notifications page when the Slack token hasn’t been set in accounts with the Slack plugin.
* The running plans page on the Plan page was adjusted to work according to the filter structure. The number of plans displayed after filtering is now shown.
* When the Change Password button is clicked on the Profile page, the page now redirects to the updated password change screen. A message with password requirements was added to the page.
* Visual design adjustments were made to the dropdown menu, and the overall appearance of the sidebar was improved. Shadow effects in the sidebar were updated.
* It is now possible to manually set the run date in the filter section on the Test Execution Report page.

#### Bug Fixes

* The Plan Delete Error encountered when some plans were deleted has been fixed.
* The 'Environment not found' error encountered due to some devices selected during the mobile device addition to the plan has been fixed.
* The issue where executions were not created on the Xray board after selecting certain fields on the plan edit page in Xray integration has been fixed.
* The issue where the Version field information selected in the plan was not visible in the execution on the Xray board has been fixed.
* The issue where the username field could be saved with a space when creating a new account on the Sign-up page has been fixed.
* The issue where the 'Sign up' button could be clicked when the 'Username' field was empty, and the page would refresh, clearing the filled information, has been fixed.
* The issue where it was not possible to log in with the most recently entered email address when logging in with different user emails has been fixed.
* The issue where clicking the 'select all' button during scenario selection on the plan edit/create page selected all scenarios instead of only the ones listed in the search results has been fixed.
* The issues where updated user information was not reflected when a user updated another user's details in the account, and the updated user information was shown in the area displaying the logged-in user's info on the dashboard after the update, have been fixed.
* The issue of inactive devices being listed in the selectable screen for plans has been fixed.
* Resolved an issue when selecting the case ID on the scenario edit page for the Testrail integration.
* The issue where a notification couldn't be added for the same email address when different test result statuses were selected in the Test Result Status field on the Plan Schedule Report page has been fixed.
* When a plan is run, if no scenario or environment is selected in the plan, appropriate error messages are now displayed to the user.
* The incorrect message displayed on the screen when plans and scenarios are selected on the Scenario and Plan listing pages has been updated.
* Resolved an issue where the search button was not working on the users page.
