# Steps

### Steps (Cucumber Step Definitions)

Steps contains reusable Cucumber step definitions that interact with the web application through Selenium.

It uses the shared WebDriver instance created in Hooks and provides common actions such as navigation, waiting, clicking, and typing.

Element interactions are performed using a key-based element repository (StoreHelper + ElementHelper) to keep feature files readable and maintainable.

***

#### Responsibilities



The Steps class is responsible for:

* Retrieving the active WebDriver instance via Hooks.getWebDriver()
* Creating helper objects used during interactions:
  * Actions for hover/mouse actions
  * WebDriverWait for synchronization
* Resolving UI elements dynamically by element key
* Performing common UI actions:
  * Navigate to a URL
  * Wait for a duration
  * Click an element
  * Type into an element
* Applying explicit waits to reduce flaky behavior

***

#### Driver and Wait Initialization

A new Steps instance is created by Cucumber, and its constructor prepares the runtime objects:

* driver is obtained from Hooks
* actions is created using the current driver
* wait is configured with:
  * Timeout: TIMEOUT\_SEC (30s)
  * Polling interval: POLL\_MS (150ms)



This ensures every step method can safely reuse the same wait and actions instances.
