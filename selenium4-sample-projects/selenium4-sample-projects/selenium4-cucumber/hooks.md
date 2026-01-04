# Hooks

### Hooks (Cucumber)

Hooks is responsible for initializing and managing the Selenium test environment for Cucumber scenarios.



Tests are executed on a remote Selenium Grid / Testinium Grid using TestiniumSeleniumDriver.

Driver lifecycle is managed using Cucumber hooks, ensuring browser sessions are created and cleaned up automatically.

***

#### Responsibilities<br>

The Hooks class is responsible for:

* Initializing the WebDriver before each scenario (@Before)
* Selecting the target browser (Chrome / Firefox) via system property (browser)
* Resolving the Selenium Grid URL from configuration sources
* Creating browser-specific options (ChromeOptions / FirefoxOptions)
* Providing shared access to WebDriver and Actions for step definitions
* Quitting the driver after each scenario (@After) to release resources

***

#### Scenario Lifecycle



**@Before beforeScenario()**

This method runs before every Cucumber scenario.



It performs:

* Browser selection:
  * Default: chrome
  * Override via: -Dbrowser=firefox
* Grid URL resolution with priority:
  1. -DnodeUrl=...
  2. -DhubURL=...
  3. SELENIUM\_REMOTE\_URL environment variable
  4. Fallback to DEFAULT\_HUB
* Driver initialization using:
  * TestiniumSeleniumDriver(gridUrl, options)
* Actions initialization:
  * actions = new Actions(driver)

***

**@After afterScenario()**

This method runs after every Cucumber scenario.

It ensures:

* The driver is quit (driver.quit())
* Static references are cleared (driver = null, actions = null)
* Selenium Grid resources are released cleanly

<br>

This keeps scenario executions isolated and prevents stale sessions.

***

#### Accessing Driver and Actions in Steps

Step definitions should retrieve shared instances via:

* Hooks.getWebDriver()
* Hooks.getActions()<br>

These methods also validate initialization and throw a clear error if the @Before hook did not run.
