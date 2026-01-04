# Pom.xml

### Maven Configuration (pom.xml)



This project uses Maven to manage dependencies and build configuration for Cucumber-based Selenium tests running on the Testinium platform.

The pom.xml includes:

* Cucumber Java and JUnit integration for executing .feature files
* Selenium 4 for browser automation
* Testinium Selenium 4 driver for Testinium Grid integration
* Supporting libraries for logging and utilities

***

### Testinium Maven Repository



The Testinium Maven repository is required to resolve Testinium-specific artifacts:

```
https://mvn.testinium.com/repository/public/
```

This repository is defined under both:

* repositories
* distributionManagement

### Key Dependencies

#### Cucumber (JUnit + Java)

```
<dependency>
  <groupId>io.cucumber</groupId>
  <artifactId>cucumber-junit</artifactId>
  <version>${cucumber.junit.version}</version>
  <scope>test</scope>
</dependency>

<dependency>
  <groupId>io.cucumber</groupId>
  <artifactId>cucumber-java</artifactId>
  <version>${cucumber.java8.version}</version>
  <scope>test</scope>
</dependency>
```

Provides the Cucumber runtime and Java step-definition support required to execute .feature files using a JUnit runner.

***

#### Selenium 4

```
<dependency>
  <groupId>org.seleniumhq.selenium</groupId>
  <artifactId>selenium-java</artifactId>
  <version>${selenium.java.version}</version>
</dependency>
```

Provides Selenium WebDriver APIs used by step implementations and hooks to automate browser interactions.

Note: Ensure only a single Selenium version is used in the project to avoid dependency conflicts.

***

#### Testinium Selenium 4 Driver (Required)

```
<dependency>
  <groupId>com.testinium</groupId>
  <artifactId>testinium-selenium4-driver</artifactId>
  <version>0.0.0.30-SNAPSHOT</version>
</dependency>
```

This dependency is mandatory when executing Selenium tests on the Testinium platform.

It enables:

* Integration with the Testinium Selenium Grid
* Platform-compatible WebDriver initialization
* Execution tracking and reporting compatibility<br>

Note: When tests are executed on Testinium, TestiniumSeleniumDriver must be used instead of the standard Selenium RemoteWebDriver.

***

#### Logging & Utilities

**Logback**

Used as the logging implementation for SLF4J.

```
<dependency>
  <groupId>ch.qos.logback</groupId>
  <artifactId>logback-classic</artifactId>
  <version>${logback.version}</version>
</dependency>
```

**Apache Commons Lang**

Provides utility classes for common Java operations.

```
<dependency>
  <groupId>org.apache.commons</groupId>
  <artifactId>commons-lang3</artifactId>
  <version>${commons.lang3.version}</version>
</dependency>
```

**Groovy (Optional)**

Included if Groovy-based utilities or scripts are used in the project.

***

### Build Plugins

#### Maven Compiler Plugin

Compiles the project using the configured Java version.

```
<plugin>
  <groupId>org.apache.maven.plugins</groupId>
  <artifactId>maven-compiler-plugin</artifactId>
  <version>3.8.1</version>
  <configuration>
    <source>21</source>
    <target>21</target>
  </configuration>
</plugin>
```

Note: The project property defines Java 21, while the compiler plugin uses Java 14.

These values should be aligned to prevent compilation issues.
