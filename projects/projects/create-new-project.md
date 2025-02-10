# Create New Project

When the Create New Project button is clicked, you will be directed to the creation screen of the project to be uploaded to the system.

The following steps should be followed to create a new project;

1. Click  _**Create New Project**_ button.

<figure><img src="../../.gitbook/assets/Create project.png" alt=""><figcaption></figcaption></figure>

2. Select the project type.

_**Selenium**_ is selected if the test will be performed on the web browser, _**Appium**_ if the mobile test will be performed, and _**Service**_ if the service tests will be performed.

<figure><img src="../../.gitbook/assets/Screenshot 2025-01-28 at 12.16.06.png" alt=""><figcaption></figcaption></figure>

&#x20;2.1  If _**Selenium**_ is selected;

<figure><img src="../../.gitbook/assets/Screenshot 2025-01-28 at 12.19.42.png" alt=""><figcaption></figcaption></figure>

a. Enter these values on the screen that pops up;

&#x20;   _1. Project Name_

&#x20;   _2. GIT Project Folder Name (This is where the test codes are located)_

&#x20;   _3. Test File Type_

_**Create From Template;**_ We'll create a sample web project based on a url give.The desired url     address is entered in the relevant field.

b. Click the _**Save**_ button to save the new project

c. Click the _**Cancel**_ button to cancel the new project definition process



2.2. If  **Appium** is selected;

<figure><img src="../../.gitbook/assets/Screenshot 2025-01-28 at 12.38.16.png" alt=""><figcaption></figcaption></figure>

a. Enter these values on the screen that pops up;

* _Project Name_
* _GIT Project Folder Name_
* _Test File Type_
* _IOS Mobile App_
* _Android Mobile App_

_**Create From Template;**_ We'll create a sample web project based on a url give.The desired url     address is entered in the relevant field.

b. Click the _**Save**_ button to save the new project

c. Click the _**Cancel**_ button to cancel the new project definition process.



2.3. If _**Service**_ is selected;

<figure><img src="../../.gitbook/assets/Screenshot 2025-01-28 at 12.45.06.png" alt=""><figcaption></figcaption></figure>

a. Enter these values on the screen that pops up;

* _Project Name_
* _Test File Type_
* _GIT Project Folder Name (This is where the test codes are located)_

_**Create From Template;**_ We'll create a sample web project based on a url give.The desired url address is entered in the relevant field.

b. Click the _**Save**_ button to save the new project

c. Click the _**Cancel**_ button to cancel the new project definition process.



3. After creating the project, an access token must be created so that the account can pull the git code of the Testinium.io project.&#x20;

{% hint style="info" %}
&#x20; The access token is created from this page;&#x20;

&#x20; _**https://git.testinium.io/-/profile/personal\_access\_tokens**_&#x20;
{% endhint %}

* It can be explained with the following example;

&#x20;    _**Username:**_ demouser&#x20;

&#x20;    _**Repo:**_ https://git.testinium.io/\_demouser/demo-project.git&#x20;

&#x20; _**Access Token:**_ AAAAAAAAAAAAAAA git clone command can be localised with the                         &#x20;

&#x20;    command;  **https://demouser@git.testinium.io/\_demouser/demo-project.git**

&#x20;    Write the access token value (AAAAAAAAAAAAA) in the password field.&#x20;

&#x20;    After the project is updated, it can be pushed with basic git commands.&#x20;
