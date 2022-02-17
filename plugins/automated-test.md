# Automated Test

**TESTINIUM CLOUD AUTOMATED TEST MANUAL**

When you use Testinium, there is an automated test option you can use to run your tests on the cloud. Automated Test enables users to take advantage of the advanced cloud testing infrastructure. You will write and modify tests on your local machine and run them on Testinium cloud. Throughout this manual, you will find a step by step tutorial on how to use the Automated Test feature on Testinium.

* Once you login to your Testinium account, click on the AUTOMATED TEST option on the upper left corner of the dashboard. This button will take you to the Code Generator page.

![](../.gitbook/assets/1)

* On the Code Generator page, you are presented with options. You can select Platform, Operating System and Browser for your test. You can also choose Screenshots and Video Recording options if you want.

![](<../.gitbook/assets/2 (2)>)

* When you scroll down the page, you will see the generated code for your test based on the options selected above. In this document, we will continue with Java code but you can select other options if you like.

![](<../.gitbook/assets/3 (2)>)

* Copy the generated code to an IDE of your choice in your local machine. We use IntelliJ here.

![](<../.gitbook/assets/4 (5)>)

* You will be required to add libraries for the code. We have added the libraries to the pom.xml file since we use Maven for dependency management.

![](<../.gitbook/assets/5 (5)>)

* Now we are all set. You can run the test and navigate back to the Testinium OPERATION REPORT tab. At the top of the list, you can see the most recent test result.

![](<../.gitbook/assets/6 (4)>)
