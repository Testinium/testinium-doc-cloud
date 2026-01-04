# CucumberRunner

### CucumberRunner (Test Execution Entry Point)

CucumberRunner is the JUnit-based entry point used to execute Cucumber feature files.

It connects Cucumber’s BDD specifications (.feature files) with the underlying step definitions and hooks, enabling tests to be run via IDE or Maven.

***

#### Responsibilities

The CucumberRunner class is responsible for:

* Bootstrapping the Cucumber runtime using JUnit
* Locating feature files from the classpath
* Triggering the execution of scenarios defined in .feature files
* Integrating Cucumber with the project’s step definitions and hooks

***

#### Execution Model

* Uses JUnit 4 via @RunWith(Cucumber.class)
* Executes all feature files located under:
  * classpath:features
* Automatically discovers:
  * Step definition classes (Steps)
  * Hook classes (Hooks)
