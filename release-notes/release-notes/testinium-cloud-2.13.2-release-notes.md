# Testinium-Cloud 2.13.2 Release Notes

#### Release Date: 07.03.2024

#### New Features

* The Testrunner, Schedular, Scaler services has been configured to communicate using the Client-Credentials Grant Type.
* Dependencies have been decoupled to reduce interdependencies between projects. The separation of structures outside of the Restapi has been completed.
* An endpoint has been created to export desired parameters from the run results to PowerBI.
* The progress bar, datepicker, and timepicker components have been updated using the NgZorro structure following the Angular 17 update.
* Following the Angular 17 update, pagination structures have been updated using the NgZorro structure.
* Following the Angular 17 update, tooltip structures have been updated using the NgZorro structure.
* Following the Angular 17 update, mat-chiplist structures have been updated using the NgZorro structure.
* Updates have been made for both Dark mode and Light mode following the updates to the style file for themes.
* Endpoints have been created to display the numbers of users, projects, plans, and scenarios on the Dashboard via cards.
* In the Scenario edit page, after the mapping process, test case id and description are now displayed. – Testrail Integration
* The titles have been updated on the Smart Prioritization Report page.
* The card titles on the Dashboard have been updated.
* The Scenario Sync page structure has been updated with the NgZorro.

#### Bug Fixes

* The bug that occurred when saving a user for the first time in the X-ray user assign section of the Plan page has been fixed.
* The bug where project information for the entered board was not retrieved in the Jira plugin has been fixed.
* The bug where information on the Sync Scenarios page was not loading upon refresh has been fixed.
