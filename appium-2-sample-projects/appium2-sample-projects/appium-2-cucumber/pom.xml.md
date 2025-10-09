# pom.xml

The pom.xml file is the configuration file of a Maven project.

Maven is a build automation tool used to compile Java projects, manage dependencies, and run tests.

For the project to run correctly, this file must exist in the project root.



Below is a detailed explanation of the key properties, dependencies, and plugins used in the Cucumber + Appium 2 project.



| java.version           | Specifies the Java version used for compilation. (Java 23 is required for execution on the Testinium platform.) |
| ---------------------- | --------------------------------------------------------------------------------------------------------------- |
| cucumber.junit.version | Defines the Cucumber-JUnit library version (4.8.0) used for running tests.                                      |

#### Distribution and Repository Configuration

These sections ensure that both your project and its dependencies are fetched and deployed correctly.

```
<distributionManagement>
    <repository>
        <id>testinium-mvn</id>
        <url>https://mvn.testinium.com/repository/public/</url>
    </repository>
</distributionManagement>

<repositories>
    <repository>
        <id>testinium-mvn</id>
        <url>https://mvn.testinium.com/repository/public/</url>
    </repository>
</repositories>
```

* distributionManagement: Defines where your build artifacts (e.g., .jar files) will be published — in this case, the private Testinium Maven repository.
* repositories: Specifies where Maven should download dependencies from. Here, it points to Testinium’s repository.



| Cucumber (JUnit 4)                         | Includes cucumber-java and cucumber-junit. These provide the step definitions and test runner for Cucumber scenarios.          |
| ------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------ |
| Appium Java Client (8.6.0)                 | Provides APIs to interact with mobile devices and the Appium server.                                                           |
| testinium-appium2-driver (0.0.13-SNAPSHOT) | Enables running mobile tests on the Testinium platform using Appium 2. Includes TestiniumAndroidDriver and TestiniumIOSDriver. |

```
<dependency>
    <groupId>com.testinium</groupId>
    <artifactId>testinium-appium2-driver</artifactId>
    <version>0.0.14-SNAPSHOT</version>
</dependency>
```
