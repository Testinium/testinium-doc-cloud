# Testinium-Cloud 2.13.7 Release Notes

#### **Release Date: 16.04.2025**

#### New Features

* Enabled screenshot support for iOS 17 and iOS 18 devices.&#x20;
* Added pie charts to test result emails and PDF reports for clearer execution summaries.&#x20;
* Extended the Plans page filters to the Scenarios page for consistent filtering.&#x20;
* Enabled linking TestRail executions to milestones and test plans.&#x20;
* Added platform-based breakdown support to dashboard pie charts.&#x20;
* Improved partial rendering by hiding only unavailable components instead of the entire page when an endpoint returns no data.&#x20;
* Updated redirect behavior of the Automated Test → Report page.&#x20;
* Added TestRail suite mode support to the integration.&#x20;
* Added informational messages for the Uninstall App After Test and Clear App Data options on the Plan Edit page.&#x20;
* Updated breadcrumb structures across the product for consistency.&#x20;
* Added logging updates for the “Plan does not contain any scenario” error.&#x20;
* Updated dashboard cards to display clearer real-time error messages.&#x20;
* Optimized dashboard load performance during company change operations.&#x20;
* Made scenario selection mandatory during plan creation.&#x20;
* Displayed warning messages as pop-ups on the Scenario Edit – IDE page.&#x20;
* Added Announcements tab to the Admin panel for delivering product updates to customers.&#x20;
* Added status filters, search, and filtering capabilities to the Dashboard Announcements tab.&#x20;
* Updated runtime and video duration calculation logic for improved accuracy.&#x20;
* Added runtime, video recording time, and executor log info to scenario result reports.&#x20;
* Enabled product announcements to be displayed as pop-ups in the Testinium UI.&#x20;
* Completed Quickrun UI design updates.&#x20;
* Designed a Quickrun onboarding wizard to guide users through the feature.&#x20;
* Added ASCII validation to group-scenario creation flow.&#x20;
* Multiple UI enhancements including consistent layout, alignment, and file-upload area resizing.&#x20;

#### Bug Fixes

* Fixed an issue where “Uninstall app after test” did not work on iOS.&#x20;
* Fixed errors encountered during file upload to a node.&#x20;
* Resolved missing executions in the Xray integration.&#x20;
* Fixed an issue where “Automatically run this plan” could not store a scheduled date.&#x20;
* Corrected timezone-related errors during Scheduler date parsing.&#x20;
* Fixed duplicate group titles appearing in execution reports for grouped scenarios.&#x20;
* Addressed failures when creating Selenium template projects in production.&#x20;
* Improved responsiveness of the Automated Test – Operation Report page.&#x20;
* Prevented multiple Jira issues from being created when the Create Jira Issue button was clicked repeatedly.&#x20;
* Resolved errors when deleting a plan.&#x20;
* Fixed incorrect group plan count calculations on Plan and Scenario pages.&#x20;
* Corrected errors during group plan creation.&#x20;
* Fixed pagination issues when deleting the only record on the last page of the Scenarios list.&#x20;
* Fixed responsive issues on the Select Test Methods area of the Create New Scenario page.&#x20;
* Investigated and resolved duplicate results in some web executions.&#x20;
* Prevented rerun attempts when no scenario was selected for rerun.&#x20;
* Fixed errors when opening the Details view under Previous Results on the Report page.&#x20;
* Corrected spacing issues in Live Testing parallelism on the Company tab.&#x20;
* Fixed random run behavior where scenarios could run on more than one device.&#x20;
* Resolved authentication issues while logging into Git accounts.&#x20;
* Fixed responsive issues on the Schedule & Notification page.&#x20;
* Ensured Scenario order updates are saved correctly on the Plan Edit page.&#x20;
* Fixed missing column values on the Report screen.&#x20;
* Resolved “font not found” error during PDF generation.&#x20;
* Fixed JSON conversion errors in Hub responseContent on production.&#x20;
* Corrected an issue where scheduled days could not be selected.
* Resolved visibility issues on the Operation Report page where certain reports could not be displayed.&#x20;
* Ensured plugin states are validated and retained when a plugin is updated on the Project Advanced tab.&#x20;
