# Create New Project

When the Create New Project button is clicked, you will be directed to the creation screen of the project to be uploaded to the system.

The following steps should be followed to create a new project;

1. Click on _**Create New Project**_ button.
2. Select the project type.

_**Selenium**_ is selected if the test will be performed on the web browser, _**Appium**_ if the mobile test will be performed, and _**Service**_ if the service tests will be performed.

<figure><img src="../../.gitbook/assets/Screenshot 2025-01-28 at 12.16.06.png" alt=""><figcaption></figcaption></figure>

&#x20;**2.1  If&#x20;**_**Selenium**_**&#x20;is selected;**

<figure><img src="../../.gitbook/assets/Screenshot 2025-01-28 at 12.19.42.png" alt=""><figcaption></figcaption></figure>

**a.** Enter these values on the screen that pops up;

&#x20;   _1. Project Name_

&#x20;   _2. GIT Project Folder Name (This is where the test codes are located)_

&#x20;   _3. Test File Type_

**Create From Template;** We'll create a sample web project based on a url give.The desired url     address is entered in the relevant field.

**b.** Click the _**Save**_ button to save the new project

**c.** Click the _**Cancel**_ button to cancel the new project definition process



**2.2. If  Appium is selected;**

<figure><img src="../../.gitbook/assets/Screenshot 2025-01-28 at 12.38.16.png" alt=""><figcaption></figcaption></figure>

**a.** Enter these values on the screen that pops up;

&#x20;    _1. Project Name_

&#x20;    _2. GIT Project Folder Name_

&#x20;    _3. Test File Type_

&#x20;    _4. IOS Mobile App_

&#x20;    _5. Android Mobile App_

**Create From Template;** We'll create a sample web project based on a url give.The desired url     address is entered in the relevant field.

**b.** Click the _**Save**_ button to save the new project

**c.** Click the _**Cancel**_ button to cancel the new project definition process.



**2.3. If Service is selected;**

<figure><img src="../../.gitbook/assets/Screenshot 2025-01-28 at 12.45.06.png" alt=""><figcaption></figcaption></figure>

**a.** Enter these values on the screen that pops up;

&#x20;     _1. Project Name_

&#x20;    _2. Test File Type_

&#x20;   _3. GIT Project Folder Name (This is where the test codes are located)_

**Create From Template;** We'll create a sample web project based on a url give.The desired url address is entered in the relevant field.

**b.** Click the _**Save**_ button to save the new project

**c.** Click the _**Cancel**_ button to cancel the new project definition process.



3. After creating the project, an access token must be created so that the account can pull the git code of the Testinium.io project.&#x20;

&#x20;    The access token is created from this page;&#x20;

&#x20;    https://git.testinium.io/-/profile/personal\_access\_tokens&#x20;

&#x20;    For example;

&#x20;    **username:** demouser&#x20;

&#x20;    **repo:** https://git.testinium.io/\_demouser/demo-project.git&#x20;

&#x20;    **access token:** AAAAAAAAAAAAA  can be localised with git clone **https://demouser@git.testinium.io/\_demouser/demo-project.git** command.&#x20;

&#x20;  Write the access token value (AAAAAAAAAAAAA) in the password field.&#x20;

&#x20;  After the project is updated, it can be pushed with basic git commands.&#x20;
