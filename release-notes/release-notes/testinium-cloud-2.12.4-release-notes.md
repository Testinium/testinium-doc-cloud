# Testinium-Cloud 2.12.4 Release Notes

#### Release Date: 07.12.2023

#### New Features

* Appcircle api integration has been provided
* Mobile private node dedication model was provided to companies.(for Android Devices)
* The Docker files for services have been created.
* The Dockerization processes have been completed. 31.10.2023 Hot Fix
* A service has been created to retrieve the report generated in the Target file for Cucumber tests.
* Services have been examined for performance improvements, and unused services have been removed.
* The Angular version upgraded on the Admin page.
* Detailed logs have been added to the Device Manager.
* The IDE page has been made responsive in Safari.
* Company plugin control has been implemented in the Live Testing usage sign.
* Sorting for “Enabled” in the Test Environments tab in Admin panel has been implemented.
* Remaining minutes on the Dashboard was displayed as days, hours, and minutes. 13.10.2023 Hot Fix
* Icons have been updated on the Plugins page. 13.10.2023 Hot Fix
* Buttons in Checkbox groups have been organized as 'select all.' 27.10.2023 Hot Fix
* Only relevant file extensions can now be uploaded on pages where IPA and APK uploads are performed. 26.09.2023 Hot Fix

#### Bug Fixes

* The issue of scenarios remaining in 'running' state in One By One runs in service tests has been resolved. 31.10.2023 Hot Fix
* The issue of tests remaining in 'running' state when starting and stopping in All in One runs in service tests has been fixed. 31.10.2023 Hot Fix
* All scenarios in plans are now executed in service tests. 31.10.2023 Hot Fix
* The issue of not being able to set the end date for some runs has been resolved. 31.10.2023 Hot Fix
* Child scenario and plan searches have been enabled in group scenarios or plans.
* A minor bug fix has been applied to the 'Show only failed tests' checkbox on the Reports page. 26.09.2023 Hot Fix
* The issue of displaying a different value in the dropdown when clicking the Create New Plan button while All Projects is selected has been resolved. 26.09.2023 Hot Fix
* Domain extension checks have been implemented on pages where email needs to be added. 26.09.2023 Hot Fix
* The issue of some buttons not appearing in Safari in Dark Mode has been fixed. 26.09.2023 Hot Fix
* The issue of selected scenarios not appearing when editing plans has been resolved. 26.09.2023 Hot Fix
* The re-uploading of canceled files during APK and IPA uploads on the Project page has been enabled. 27.10.2023 Hot Fix
* The issue of Name, Surname, and email information not appearing in the Account Information section has been resolved. 26.09.2023 Hot Fix
* The issue of duplicate success messages in the Automated test section has been resolved.
* A bug fix has been applied to the Account Information page in Dark mode. 26.09.2023 Hot Fix
* The refresh error in the Delete Report section has been resolved. 13.10.2023 Hot Fix
* The issue of -1 appearing in the “Select a Project” tab on the Plan page has been resolved. 13.10.2023 Hot Fix
* The issue of previously selected tags not appearing in mapped scenarios in Xray plugin integration has been resolved. 13.10.2023 Hot Fix
* A minor bug fix has been applied to Cancel buttons. 13.10.2023 Hot Fix
* The issue of the old selection being visible in the refreshed page when selecting a group while editing a plan has been resolved. 13.10.2023 Hot Fix
* The issue of the cached plan ID appearing on the screen when the project is selected has been resolved. 27.10.2023 Hot Fix
* Pagination now starts from page 1 when changing the project on the Scenario and Plan pages. 27.10.2023 Hot Fix
* Updating project details when changing the project from the top bar in the Project detail section has been ensured. 27.10.2023 Hot Fix
* The issue of the message section not being responsive in the link opened by the 'create copy URL' button on the Reports page has been resolved. 27.10.2023 Hot Fix
* Log display according to the type of run has been enabled in the link-relayed report. (Selenium for Web/ Appium for Mobile) 27.10.2023 Hot Fix
* The issue of the cached project ID sometimes appearing on the screen when the project is selected has been resolved.
* A minor bug fix has been applied to the Testinium IO report section when copying a report.
* The issue of some devices appearing twice when selecting an environment on the Plan page has been resolved.
* The issue of receiving duplicate messages when an Apk or Ipa is uploaded on the Automated Test page has been resolved. 26.09.2023 Hot Fix
* The 'Select a Project' section now comes as selected or as 'All Project' when creating a Scenario Group. 27.10.2023 Hot Fix
* The issue of the group creation button appearing empty when editing a plan has been resolved.
* The issue of duplicate requests in the Advanced tab of Project Details has been resolved.
