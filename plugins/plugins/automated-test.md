# Automated Test

**TESTINIUM CLOUD AUTOMATED TEST MANUAL**

Testinium provides an **Automated Test** feature that allows you to run your tests seamlessly on the cloud. This feature enables users to utilize Testinium's advanced cloud testing infrastructure. You can write and modify tests on your local machine and execute them directly on the Testinium cloud.

This manual provides a step-by-step guide to using the **Automated Test** feature in Testinium.

1. Log in to your Testinium account.
2. Click on the **Automated Test** option located in the upper-left corner of the dashboard.
   * This will redirect you to the **Code Generator** page.

![](<../../.gitbook/assets/Screenshot 2025-01-27 at 17.14.56.png>)

* On the **Code Generator** page, you will see various options. You can select the **Platform**, **Operating System**, and **Browser** for your test. Additionally, you can enable the **Screenshots** and **Video Recording** options if desired.

![](<../../.gitbook/assets/Screenshot 2025-01-27 at 17.16.16.png>)

* When you scroll down the page, the generated code for your test, based on the options selected above, will be displayed. In this document, we will proceed with **Java** code; however, you may choose other options if preferred.

![](<../../.gitbook/assets/Screenshot 2025-01-27 at 17.17.12.png>)

* Copy the generated code to an IDE of your choice on your local machine. In this guide, we will use **IntelliJ** as an example.

![](<../../.gitbook/assets/4 (5)>)

* You will need to add the required libraries for the code. Since we are using **Maven** for dependency management, the libraries have been added to the **pom.xml** file.

![](<../../.gitbook/assets/5 (5)>)

* Now everything is ready. You can run the test and navigate to the **Operation Report** tab in Testinium. At the top of the list, you will find the most recent test result.

![](<../../.gitbook/assets/6 (4)>)
