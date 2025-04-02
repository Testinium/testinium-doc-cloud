# Testinium-Cloud 2.13.1 Release Notes

#### Release Date: 09.02.2024

#### New Features

* Frontend Angular version upgraded to 17. Libraries of different structures used in the project were removed and the Ng-Zorro library was integrated.
* Directives and Components used in the frontend project have been transformed into standalone structures.
* The structures on the Plan edit – Schedule & Notification page have been updated with the Ng-Zorro library.
* The datepicker structure has been updated with the Ng-Zorro library.
* All Ng-Select components in the frontend project have been updated to Nz-Select.
* The Ng-notification structure has been updated in the frontend project.
* The Ngx-bootstrap/sortable and Ngx-bootstrap/tabs components have been updated in the frontend project.
* The @angular/material/button structure for the Dashboard has been updated with the Ng-Zorro library.
* The architecture for the dynamic executor development has been created, and the POC has been completed.
* Error message has been updated for errors encountered during the upload of the application file (ipa/apk) on the Automated Test page.
* In the Account section, the ability to make custom date selections has been enabled for defining package details for the customer.
* Dependencies have been decoupled to reduce interdependencies between projects.
* The Notification Service has been configured to communicate using the Client-Credentials Grant Type.
* The Admin page's Devices tab now includes iOS license information for devices.
* A device model search feature has been added to the Device create page.
* The Plan edit page now includes a scroll bar for device listing in the environment selection section.

#### Bug Fixes

* The 'Test does not run' error encountered in Karate tests has been fixed.
* The bug of a scenario running multiple times in the same environment during mobile runs has been fixed. (For cross runs)
* The issue where runs continued using the old schedule information even after a new schedule was set for the plan has been fixed.
* The "Environment not active!" error has been fixed.
* A minor bug in the date selections for "Repeat" and "Automatically run this plan" in scheduled plans on the Schedule & Notification page has been fixed.
* The bug where APK files uploaded to the project were being deleted after a run has been fixed.
* The error occurring when making a custom date selection in the Account section has been fixed.
* A minor bug in adding packages to users in the Account section has been fixed.
* A minor bug in the "Copy URL" button on the Scenario edit page has been fixed.
