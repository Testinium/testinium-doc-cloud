# Testinium-Cloud 2.13.8 Release Notes

#### Release Date: 16.04.2025

#### New Features

* A checkbox was added to the project creation page to mark the IPA as signed with an Apple Developer Enterprise license, so it can be installed on the device without re-signing.
* The trust prompt that appears when non-resignable IPAs are installed is now automatically confirmed.
* Minimum supported device versions are now displayed on the project page when IPA or APK files are uploaded, making it easier to manage selected devices in the plan.
* Users are now informed on the plan edit page if any previously selected devices do not meet the current minimum OS/SDK requirements, to prevent version-related errors.
* The process of adding iOS licenses during IPA signing has been reviewed and improved.
* An "Announcement" section has been added to keep users informed about important updates, maintenance activities, and system messages, directly within the product.

<figure><img src="../../.gitbook/assets/Screenshot 2025-04-18 at 18.31.34.png" alt=""><figcaption></figcaption></figure>

* New error messages were added to help users better understand and analyze issues during mobile test executions.
* The process of building test code was updated to stabilize executor resource usage.
* A Server Status Page has been introduced to provide users with real-time information about maintenance activities, system performance, and service interruptions.
* A loading indicator was added to the “File Content” field on the scenario edit page to improve the user experience during the loading process.
* With the Angular 19 upgrade, UI components and shared logic were updated to match modern standards, improving speed and design consistency. Additionally, buttons, tables, and checkboxes across the interface were standardized for a more consistent user experience.

#### Bug Fixes

* Fixed a bug that prevented the automatic confirmation of the trust prompt during app installation.
* Resolved an error related to third-party authentication during the login process.
* Resolved a bug that triggered a new package creation when editing a private package.
