# Tunnel

Testinium Virtual Tunnel

Testinium Virtual Tunnel is a proxy server that provides a secure connection from Testinium’s mobile device farm and virtual browsers to your application under test or website hosted behind a corporate firewall. The secure tunnel is only accessible from our testing environment.

Testinium Virtual Tunnel is a jar package that include all component needed and can be launched by a console application. This jar connets application with Testinium dedicated machine and opens Tunnel. By this way connection provided on same IP address. You can also use CLI to run a Tunnel.

**Creating Tunnel**

**Downloading Client**\
You need to go to https://testinium.io/user/account/tunnel and download the jar file.

![](<../../.gitbook/assets/1 (2)>)

### **Creating a Tunnel Connection**

Testinium Tunnel’s page allows you to create a Tunnel Connection. You need to go to https://testinium.io/user/account/tunnel and click “Create Tunnel” and you’ll be welcomed by the “Create Tunnel” page.

![](<../../.gitbook/assets/2 (4)>)

**Direct Domains** field is for domains that you don’t want to reach via Testinium’s Tunnel like a 3rd party application that runs behind your application. (Google Analytics, Hotjar, etc..)

Now your tunnel is created. When you save this information, you will receive a Tunnel ID on the previous page.\\

![](<../../.gitbook/assets/3 (5)>)

### Running the Tunnel

When you download the client, it will be a zip file containing all the components to run the jar file. The JAR file is in the lib folder.

\
There are two ways of running the Tunnel.

First way of running application with credentials.

\
![](<../../.gitbook/assets/4 (3)>)

java -jar tunnel-cli-1.2.jar -u username -p TestiniumAccessKey -t TunnelId

After running the command, you need to see below logs. This means that the Tunnel has started successfully.

![](<../../.gitbook/assets/5 (4)>)

Second way of running application

You can also run the Tunnel as a command line application by using the command below\\

java -jar tunnel-cli-1.2.jar\\

Then you will be welcomed by the screen below

![](<../../.gitbook/assets/6 (5)>)

You can enter your credentials and select the specific tunnel by following the commands.

Ok, now everything is set up. The tunnel is created and Tunnel application is running. The last thing we should do is adding our Tunnel ID as a “Desired Capabilities” to our Selenium or Appium code.

#### Adding Tunnel to Desired Capabilities

In order to run your test in Testinium’s Selenium Grid, you need to add some desired capabilities. Those capabilities include the browser name, browser version and other supporting information about the test environment. To be able to proxy our request to Testinium VPN Tunnel, you need to add one more desired capability.

Below you can find the sample test code to create a RemoteWebDriver.

WebDriver driver = null;

DesiredCapabilities capabilities = new DesiredCapabilities();

capabilities.setCapability("key", KEY);

capabilities.setCapability(CapabilityType.PLATFORM, "LINUX");

capabilities.setCapability(CapabilityType.BROWSER\_NAME, "firefox");

capabilities.setCapability(CapabilityType.VERSION, "64");

capabilities.setCapability(CapabilityType.TAKES\_SCREENSHOT, true);

capabilities.setCapability("recordsVideo", true);

capabilities.setCapability("screenResolution", "WXGA\_P");

capabilities.setCapability("testinium:tunnel.id", "8fda76d3s-089a-42e7-9c9c-fe9293232692");

try {

driver = new RemoteWebDriver(new URL("http://hub.testinium.io/wd/hub"), capabilities);

} catch (MalformedURLException e) {

e.printStackTrace();

}

**Happy Testing with VPN Tunnel.**
