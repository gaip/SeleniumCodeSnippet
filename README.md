# Selenium Code Snippet


##Table of Contents

- [Download Driver](#Driver-Download)
    - [Composer](#composer)
    - [TYPO3](#typo3)
    - [Database](#database)
- [Setup](#setup)
    - [Upload the page tree file](#upload-the-page-tree-file)
    - [Go to the import view](#go-to-the-import-view)
    - [Import the uploaded page tree file](#import-the-uploaded-page-tree-file)
- [License](#license)
- [Links](#links)
- 



## Driver Download


I am **bold**



## Firefox Driver
```java
WebDriver driver = new FirefoxDriver();           //Firefox Driver
```


## Chrome Driver
```java
System.setProperty("webdriver.chrome.driver", "/path/to/chromedriver");
WebDriver driver = new ChromeDriver();
```

## Internet Explorer Driver
```java
System.setProperty("webdriver.ie.driver", "C:\\Selenium\\IEDriverServer.exe");
WebDriver driver = new InternetExplorerDriver();
```

## Android Driver
```java
WebDriver driver = new AndroidDriver()            
```

## Safari Driver
```java
WebDriver driver = new SafariDriver();            
```

## iPhone Driver
```java
WebDriver driver = new IPhoneDriver();            
```

## HTML Unit
```java
WebDriver driver = new HtmlUnitDriver()           
```

## RemoteWebDriver - Selenium Grid
```java
DesiredCapabilities safari = IOSCapabilities.iphone("Safari");
RemoteWebDriver driver = new RemoteWebDriver(new URL("http://localhost:5555/wd/hub"), safari);
```

## Find Elements

```java
//Find element by ID:
WebElemnt we1 = driver.findElement(By.id("Elementid"))

//Find element by element name:
WebElemnt we1 = driver.findElement(By.name("ElementName"))


//Find element by tagname:, get all the links
WebElemnt we1 = driver.findElement(By.tagName("a"))


//Find element by class name:
WebElemnt we1 = driver.findElement(By.className("ElementClassName"))

//Find element by CSS Selector:
WebElemnt we1 = driver.findElement(By.cssSelector("input[value='google']"));

//Find element by element link text
WebElemnt we1 = driver.findElement(By.linkText(“click here”))

//Find element by partial element link text
WebElemnt we1 = driver.findElement(By.partialLinkText(“clic”))

//Find element by xpath
WebElemnt we1 = driver.findElement(By.Xpath(“clic”))
```

## Xpath

```java

Xpath Locator based on id of element:
xpath=//input[@id='name']

Xpath Locator based on name of element: 
xpath=//input[@name='email']

Xpath Locator based on class of element: 
xpath=//input[@class='button']

Xpath Locator based on value of element: 
xpath=//input[@value='Submit ']

Xpath Locator based on containing text by element: 
xpath=//p[contains(text(),'Name')]


//1.Identifying Xpath using full path of XML
xpath=//body/div[3]/form/fieldset/input[2]  
//// Here //body is the main root node, /div[3] describes the 3rd div child node of parent node body, /form describes the child node form of parent node div[3], /fieldset describes the child node fieldset of parent node form, /input[2] describes the 2nd input child node of parent node fieldset.


//2.Writting Xpath using last()
//// Here /input[last()-2] describes the 3rd upper input node(input[2]) from last input node.
xpath=//body/div[3]/form/fieldset/input[last()-2]  
//// Here /*[last()-3] describes the 4th upper  node(input[2]) from last node.
xpath=//body/div[3]/form/fieldset/*[last()-3]   


//3.Xpath locator using @ and attribute
//// Here /input[@type='search'] describes the input node having attribute type='search'.
xpath=//body/div[3]/form/fieldset/input[@type='search']   


//4.Xpath expression using @ and attribute
// Here /input[@accesskey='F'] describes the input node having attribute @accesskey='F'. Another way of same is as bellow.
xpath=//body/div[3]/form/fieldset/input[@accesskey='F']   


//5. Xpath syntax using @ and attribute
// Here //input[@accesskey='F'] describes the input node having attribute @accesskey='F'. Try it by using it in above example.
xpath=//input[@accesskey='F']  

6. Xpath example using @ and attribute
// Here /input[@type='search'] describes the input node having attribute type='search'. Try it by using it in above example.
xpath=//input[@type='search']   

7. XML Xpath using /descendant:: keyword
// Here i have used descendant in between. In this case i have described only starting node div with attribute class='search-container' and final node input with accesskey='F' attribute. So not need to describe in between nodes. Try it by using it in above example.
xpath=//div[@class='search-container']/descendant::input[@accesskey='F']   

8. Xpath query example using contains keyword
//Here i have used contains keyword to identify id attribute with text "searchInput". Try it by using it in above example.
xpath=//input[contains(@id, "searchInput")]   

9. xpath using and with attributes
//In this example, It will look at two attributes in input node. Try it by using it in above example.
xpath=//input[contains(@id, "searchInput") and contains(@accesskey,"F")]   

10. XML xpath value value using position()
//This xpath will select input node which is on number 2 position and it is for input text box as shown in image. Try it by using it in above example.
xpath=//div[@class='search-container']/descendant::input[position()=2]   

11. Using starts-with keyword
//  In this example, It will find input node with attribute is 'type' and its value is starting with 's' (here it will get type = 'search').
xpath=//input[starts-with(@type, "s")]    

12. Using OR (|) condition with xpath
//input[@id='searchInput']
xpath=//input[@accesskey='F'] | 
// In both these example, it will find input text box with accesskey='F' or @id='searchInput'. If any one found then it will locate it. Very useful when elements appears alternatively.
xpath=//input[@accesskey='F' or @id='searchInput']  

13. Using wildcard * with to finding element xpath
xpath=//*[@accesskey='F'] 

14. Finding nth child element of parent
//This xpath is for search text box. Here, /*[3] describes the 3rd child element of body which is div[3]. Same way *[2] describes the 2nd child element of fieldset which is input[2]

xpath=//body/*[3]/form/fieldset/*[2]  


Xpath Examples for drop down
1. xpath=//body/div[3]/form/fieldset/select
2. xpath=//body/div[3]/form/fieldset/select[last()]
3. xpath=//body/div[3]/form/fieldset/select[@id='searchLanguage']
4. xpath=//body/div[3]/form/fieldset/select[@name='language']
5. xpath=//div[@class='search-container']/descendant::select[@name='language']
6. xpath=//select[contains(@id, "searchLanguage")]
7. xpath=//div[@class='search-container']/descendant::select[position()=1]
8. xpath=//body/div[3]/form/fieldset/select[count(*)>1]

```


## CSSSelector

```java


(1) Id:
//div[@id='panel']



Class:
//div[@class='panelClass']

//div[@class='panelClass1 panelClass2']

Any Attributes:
//div[@name='continue']
//input[@type='button']

Direct Child:
//ul/li


Child or Subchild:
//ul//li

nth Child:
//ul[@id='drinks']/li[5]


Parent of an element:
//li[@class='blue']/..

Next Sibling:
//li[@class='blue']/../li[2]
//li[@class='blue']/../li[3]


Match by Innertext:
//a[contains(text(),'Sign in')]
//a[contains(string(),'Sign in')]

By Attribute
//a[contains(@id,’signup’)]
//a[contains(@id,’link-signup’)]
//a[contains(@id,’link)] 


(10) Match by Sub-string:

(i) Match a Sub-string(pattern):
//div[contains(@id,'pattern')]

(ii) Match a prefix:
//div[starts-with(@id,"prefixString")]

(iii) Match a suffix:
//div[ends-with(@id,"suffixString")]



contains()
//div[contains(@id,’module’)]
//*[@id=’regular-expression-syntax’]//h2[contains(text(), ‘7.2.1. Regular Expression Syntax’)]

concat()
concat(//*[@id=’checking-for-a-pair’]/h3/text(), //*[@id=’simulating-scanf’]/h3/text())

normalize-space()
//*[@id=’sb_form_q’][normalize-space(@value)=’asd asd’]

starts-with()
//div[starts-with(@id,’module’)]
string-length()
The string-length returns the number of characters in the string
string-length(//*[@id=’regular-expression-syntax’]/h2/text())

substring()
substring(//*[@id=’regular-expression-syntax’]/h2/text(), 2, 30)

substring-after()
//div[substring-after(@id,’finding-‘)]
//*[starts-with(@id,’finding’) and substring-after(@id,’finding-all-adverbs-‘)]

substring-before()
//div[substring-before(@id,’objects’)]
ancestor
Ancestor lets you select any ancestors [e.g., Parent and Grandparent] of the current node.
//*[@id=’regular-expression-syntax’]/ancestor::div[5]/div[2]
//*[@id=’regular-expression-syntax’]/ancestor::*

ancestor-or-self
Ancestor-or-self lets you select any ancestors [e.g., Parent and Grandparent] of the current node including the current node.
//*[@id=’regular-expression-syntax’]/ancestor-or-self::div[1]
//*[@id=’regular-expression-syntax’]/ancestor-or-self::*

attribute
Attribute returns all the attributes in the current node.
//*[@class=’sphinxsidebarwrapper’]/attribute::*
//*[@id=’sidebarbutton’]/attribute::title

child
Child returns all the children in the current node.
//*[@class=’sphinxsidebarwrapper’]/child::*
//*//child::h3

descendant
Descendant lets you select all descendants [e.g., Children and Grandchildren] of the current node.
//*[@class=’this-page-menu’]/descendant::*
//*[@class=’this-page-menu’]/descendant::li[2]
//*[@class=’documentwrapper’]/descendant::div[position()=3]

descendant-or-self
Descendant-or-self lets you select all descendants [e.g., Children and Grandchildren] of the current node including the current node.
//*[@class=’this-page-menu’]/descendant-or-self::*
//*[@id=’searchbox’]/descendant-or-self::form[@class=’search’]/input[2]

following
Following returns all in the document after the closing tag of the current node.
//*[@class=’clearer’]/following::*

following-sibling
Following-sibling returns all the sibling after the closing tag of the current node.
//*[@class=’related’]/following-sibling::*
//*[@class=’related’]/following-sibling::div[3]

//Absolute XPath
web_element_name=html/body/div[30]/div[2]/div[2]/div/div/div/div[1]/table/tbody/tr/td[1]/table/tbody/tr[2]/td[2]/em/button
 

WebElement userName = driver.findElement(By.cssSelector("html body div div form input"));
WebElement userName = driver.findElement(By.cssSelector("input"));
WebElement userName = driver.findElement(By.cssSelector("div > a"));
WebElement userName = driver.findElement(By.cssSelector("div a"));
WebElement userName = driver.findElement(By.cssSelector("input#username"));


WebElement userName = driver.findElement(By.cssSelector("#username"));
WebElement userName = driver.findElement(By.cssSelector("input.classname"));


WebElement userName = driver.findElement(By.cssSelector(".classname"));
WebElement previousButton = driver.findElement(By.cssSelector("img[alt='Previous']"));
List<WebElement> imagesWithAlt = driver.findElements(By.cssSelector("img[alt]"));
WebElement previousButton = driver.findElement(By.cssSelector("header[id^='page-']"));
WebElement previousButton = driver.findElement(By.cssSelector("header[id$='page-']"));
WebElement previousButton = driver.findElement(By.cssSelector("header[id*='page-']"));  





WebElement userName = driver.findElement(By.xpath("html/body/div/div/form/input"));
WebElement userName = driver.findElement(By.xpath("//input"));
WebElement userName = driver.findElement(By.xpath("//div/a"));
WebElement userName = driver.findElement(By.xpath("//div//a"));
WebElement userName = driver.findElement(By.xpath(".//*[text()='Первая ссылка']/.."));
WebElement userName = driver.findElement(By.xpath("//input[@id='username']"));
List<WebElement> imagesWithAlt = driver.findElements(By.xpath ("img[@alt]"));
WebElement userName = driver.findElement(By.xpath("//input[@id='username']/.."));


//Css Selector Using ID Selector
var TxtBoxElement = driver.FindElement(By.CssSelector("input#userid"));

//Css Selector Using Class Selector
var TxtBoxElement = driver.FindElement(By.CssSelector("input.txtuser"));

WebElement cssele = driver.findElements(By.cssSelector("input.textboxcss.top"));


//Css Selector Using Attributes Selector
var TxtBoxElement = driver.FindElement(By.CssSelector("input[id=userid]"));
var BtnElement = driver.FindElement(By.CssSelector("button[class=btnclass]"));
var AnchorElement = driver.FindElement(By.CssSelector("a[title=myLink]"));
WebElement cssele = driver.findElements(By.cssSelector("input#txtName[name=’taComment’]"));

//Tag, Class and Attribute

WebElement cssele = driver.findElements(By.cssSelector("input.textboxcss [name=’taComment’]"));

//Css Selector Using Pattern Matching
//1. Starts With (prefix)
var TxtBoxElement = driver.FindElement(By.CssSelector("input[id^='user']"));

//2. Ends With (suffix)
var BtnElement = driver.FindElement(By.CssSelector("button[class$='btn']"));

//3. Contains
var AnchorElement = driver.FindElement(By.CssSelector("a[href*='yahoo'] "));


//CSS Selector using Parent (indirect child)
var ElementA = driver.FindElement(By.CssSelector("div#parentdiv input.txtclass]"));
var ElementB = driver.FindElement(By.CssSelector("div#parentdiv id=anchor]"));


//CSS Selector using Parent (direct child)
var ElementA = driver.FindElement(By.CssSelector("div#parentdiv > input.txtclass]"));
var ElementB = driver.FindElement(By.CssSelector("div#parentdiv  > id=anchor]")


//nth-chilld()
WebElement cssele = driver.findElements(By.cssSelector("li:nth-child(n)"));

//Inner text
WebElement cssele = driver.findElements(By.cssSelector("span:contains(‘Upload you pic‘)"));


WebElement ele1 = driver.findElement(By.cssSelector(".primary-btn"));
WebElement ele2 = driver.findElement(By.cssSelector("btn.primary-btn"));
WebElement ele3 = driver.findElement(By.cssSelector("btn.primary-btn"));  

WebElement Email = driver.findElement(By.cssSelector("input[id=email]"));

driver.FindElement(By.CssSelector("#rightbar > .menu > li:nth-of-type(3) > h5"));


IList<IWebElement> hotBanners = driver.FindElements(By.CssSelector(".ban.hot"));
IWebElement banUsStates = hotBanners[3];


driver.findElement(By.cssSelector(“input[id=’Email’]”)).sendKeys(“abcd”);
driver.findElement(By.cssSelector(“input[name=’Passwd’]”)).sendKeys(“Rahul”);

//using multiple attributes
//driver.findElement(By.cssSelector(“input[id=’signIn’][value=’Sign in’]”)).click();

//using class name: 2 special chars. . for class and # for id

//driver.findElement(By.cssSelector(“input.rc-button”)).click();

//using multiple classes
//driver.findElement(By.cssSelector(“input.rc-button.rc-button-submit”)).click();

//using #
//driver.findElement(By.cssSelector(“input#signIn”)).click();

//^=start with $=ends with *=contains

/*driver.findElement(By.cssSelector(“input[id^=’Em’]”)).sendKeys(“abcd”);

driver.findElement(By.cssSelector(“input[id$=’wd’]”)).sendKeys(“abcd”);

driver.findElement(By.cssSelector(“input[value*=’n i’]”)).click();*/

driver.findElement(By.cssSelector(“css=a:contains(‘Sign in’)”)).click();


1. Selenium CSS locator using Tag and any Attribute
css=input[type=search] \\\\ This syntax will find "input" tag node which contains "type=search" attribute.

css=input[id=searchInput] \\\\ This syntax will find "input" tag node which contains "id=searchInput" attribute.

css=form input[id=searchInput]  \\\\  This syntax will find form containing "input" tag node which contains "id=searchInput" attribute.

(All three CSS path examples given above will locate Search text box.)

2. Selenium CSS locator using Tag and ID attribute
css=input#searchInput \\\\ Here, '#' sign is specially used for "id" attribute only. It will find "input" tag node which contains "id=searchInput" attribute. This syntax will locate Search text box.

3. Selenium CSS locator using Tag and class attribute
css=input.formBtn  \\\\  Here, '.' is specially used for "class" attribute only. It will find "input" tag node which contains "class=formBtn" attribute. This syntax will locate Search button (go).

4.  Selenium CSS locator using tag, class, and any attribute
css=input.formBtn[name=go]  \\\\ It will find "input" tag node which contains "class=formBtn" class and "name=go" attribute. This syntax will locate Search button (go).

5. Tag and multiple Attribute CSS locator
css=input[type=search][name=search] \\\\  It will find "input" tag node which contains "type=search" attribute and "name=search" attribute. This syntax will locate Search text box.

6. CSS Locator using Sub-string matches(Start, end and containing text) in selenium
css=input[id^='search']  \\\\  It will find input node which contains 'id' attribute starting with 'search' text.(Here, ^ describes the starting text).

css=input[id$='chInput']  \\\\  It will find input node which contains 'id' attribute starting with 'chInput' text. (Here, $ describes the ending text).

css=input[id*='archIn']  \\\\  It will find input node which contains 'id' attribute containing 'archIn' text. (Here, * describes the containing text).

(All three CSS path examples given above will locate Search text box on page of software web application.)

7. CSS Element locator syntax using child Selectors
css=div.search-container>form>fieldset>input[id=searchInput]  \\\\  First it will find div tag with "class = search-container" and then it will follow remaining path to locate child node. This syntax will locate Search text box.

8. CSS Element locator syntax using adjacent selectors
css=input + input  \\\\  It will locate "input" node where another "input" node is present before it on page.(for search tect box).

css=input + select or css=input + input + select \\\\  It will locate "select" node, where "input" node is present before it on page(for language drop down).

9. CSS Element locator using contains keyword
css=strong:contains("English")  \\\\ It will looks for the element containing text "English" as a value on the page.




```



## Navigation

```java

driver.navigate().refresh();

//Go back to the last visited page
driver.navigate().back();

//go forward to the next page
driver.navigate().forward();


```

## Waiting

```java
WebDriverWait wait = new WebDriverWait(driver, 30);
WebElement element = wait.until(ExpectedConditions.elementToBeClickable(By.id("id123")));
```

##Keyboard Interaction
```java

// Configure the Action
Actions action = new Actions(driver);

// To click on the element
action.moveToElement(element).click().perform();


//Multiple Actions
Actions action = new Actions(driver);
action.movetoElement("webelement")
.click()
.sendkey("aaa")
.doubleClick("webelement")
.contextClick()
.keyDown(Keys.Down)
.build()
.perform()



```

##Mouse Interaction
```java

```

##Take A Screenshot On The Page
```java
File snapshot =((TakesScreenshot)driver).getScreenshotAs(OutputType.FILE);
```

##Execute A JavaScript
```java
JavascriptExecutor js = (JavascriptExecutor) driver;
String js = "document.getElementsByName('fillname')[0].value='Selvi'";
js.executeScript(js);


private static void addJQuery (JavascriptExecutor js) {

    String script = "";

    boolean needInjection = (Boolean)(js.executeScript("return this.$ === undefined;"));
    if(needInjection) {
        URL u = Resources.getResource("jquery.js");
        try {
            script = Resources.toString(u, Charsets.UTF_8);
        } catch(IOException e) {
            e.printStackTrace();
        }
        js.executeScript(script);
    }
}



WebElement element = (WebElement) js.executeScript("return jQuery.find('#hplogo');");



```

Upload A File 
```java
this.driver.Navigate().GoToUrl(
        @"https://demos.telerik.com/aspnet-ajax/ajaxpanel/application-scenarios/file-upload/defaultcs.aspx");
WebElement element = driver.FindElement(By.Id("ctl00_ContentPlaceholder1_RadUpload1file0"));
String filePath = @"D:\Projects\PatternsInAutomation.Tests\WebDriver.Series.Tests\bin\Debug\WebDriver.xml";
element.SendKeys(filePath);
```


##Scroll Up, Down Or Anywhere On A Page
```java
JavascriptExecutor jsx = (JavascriptExecutor) driver;
//Vertical scroll - down by 100 pixels
jsx.executeScript("window.scrollBy(0,100)", "");
//Vertical scroll - up by 55 pixels (note the number is minus 55)
jsx.executeScript("window.scrollBy(0,-55)", "");
//Horizontal scroll - right by 20 pixels
jsx.executeScript("window.scrollBy(20,0)", "");
//Horizontal scroll - left by 95 pixels (note the number is minus 95)
jsx.executeScript("window.scrollBy(-95,0)", "");


//Drag and Drop
this.driver.Navigate().GoToUrl(@"http://loopj.com/jquery-simple-slider/");
WebElement element = driver.FindElement(By.XPath("//*[@id='project']/p[1]/div/div[2]"));
Actions move = new Actions(driver);
move.DragAndDropToOffset(element, 30, 0).Perform();

```




```java
import org.openqa.Selenium.Proxy

FirefoxProfile profile = new FirefoxProfile();
String PROXY = "999.999.999.999:9999";
Proxy proxy = new Proxy();
proxy.HttpProxy=PROXY;
proxy.FtpProxy=PROXY;
proxy.SslProxy=PROXY;
profile.SetProxyPreferences(proxy);
FirefoxDriver driver = new FirefoxDriver(profile);
```




20. File Download

```java
FirefoxProfile Prof = new FirefoxProfile();
Prof.setPreference("browser.download.dir", "D:\\java prj");
Prof.setPreference("browser.download.folderList", 2);
Prof.setPreference("browser.helperApps.neverAsk.saveToDisk","application/zip");
  
WebDriver driver = new FirefoxDriver(Prof);
driver.get("http://seleniumhq.org/download/");
driver.manage().timeouts().implicitlyWait(3,TimeUnit.MINUTES);
driver.findElement(By.xpath("//a[@name='client-drivers']/table/tbody/tr[1]/td[4]/a")).click();
```

##Alert Screen

```java

**Import org.openqa.selenium.Alert**

WebDriverWait wait = new WebDriverWait(driver, 2);
wait.until(ExpectedConditions.alertIsPresent());

//Switch to Alert
Driver.switchTo().alert();

//Object Creation for Alert class
Alert alert = driver.switchTo().alert();
alert.getText();

//Accept the Alert
alert.accept();   

//Reject the Alert
alert.dismiss();

```


##IFrames

```java
//By finding all the web elements using iframe tag
List<WebElement> iframeElements = driver.findElements(By.tagName("iframe"));
System.out.println("The total number of iframes are " + iframeElements.size());
		
//Switch by frame ID
driver.switchTo().frame("IFRAMEGOOGLEADID");
		
//Switch by Index
driver.switchTo().frame(0);

//Switch by frame name
driver.switchTo().frame("iframename");
		
//Switch to Frame by WebElement
driver.switchTo().frame(driver.findElement(By.id("IFRAMEGOOGLEADID")));

//Switching back to Main page from Frame
driver.switchTo().frame(0);
driver.switchTo().defaultContent();

//Wwitch to the parent frame and then switch to the child frame
driver.switchTo().frame("ParentFrame").switchTo().frame("ChildFrame");
```


## Window Handle

```java

//Return a string of alphanumeric window handle
String  handle= driver.getWindowHandle();

//get the window handle of all the current windows
Set<String> windows = driver.getWindowHandles();
Iterator<String> itr = windows.iterator();

//loop thru 
for (String handle : driver.getWindowHandles()) {
    driver.switchTo().window(handle);}
}




//patName will provide you parent window
String patName = itr.next();

//chldName will provide you child window
String chldName = itr.next();

//Switch to child window
driver.switchto().window(chldName);

handles.remove(chldName);

//Do normal selenium code for performing action in child window

//To come back to parent window
driver.switchto().window(patName);



//To close all the other windows except the main window.
public static boolean closeAllOtherWindows(String openWindowHandle) {
	Set<String> allWindowHandles = driver.getWindowHandles();
	for (String currentWindowHandle : allWindowHandles) {
		if (!currentWindowHandle.equals(openWindowHandle)) {
			driver.switchTo().window(currentWindowHandle);
			driver.close();
		}
	}
	
	driver.switchTo().window(openWindowHandle);
	if (driver.getWindowHandles().size() == 1)
		return true;
	else
		return false;
}
```


## Window Handle


```java
//Implicitly Wait Command
driver.manage().timeouts().implicitlyWait(10, TimeUnit.SECONDS);


//Explicit Wait Command
WebDriverWait wait = new WebDriverWait(driver, 10);
WebElement element = wait.until(ExpectedConditions.elementToBeClickable(By.id(>someid>)));

//PageLoadTimeout Command
driver.manage().timeouts().pageLoadTimeout(100, SECONDS);

//SetScriptTimeout Command
driver.manage().timeouts().setScriptTimeout(100,SECONDS);

//Sleep Command
thread.sleep(1000)

```


alertIsPresent() : Is Alert Present?
elementSelectionStateToBe: Is the element selected?
elementToBeClickable: Is the element clickable?
elementToBeSelected: Element is selected
frameToBeAvailableAndSwitchToIt: Is frame available and selected?
invisibilityOfElementLocated: Is the element invisible?
presenceOfAllElementsLocatedBy: All elements presence location.
refreshed: Wait for a page refresh.
textToBePresentInElement: Is the text present for a particular element?
textToBePresentInElementValue: Is the element value present for a particular element?
visibilityOf: Is the element visible?
titleContains: Is that title contain?



//Handle browser based authentication using Selenium Webdriver
driver.get("http://username:password@selvi.com/");


```java

//Switch Between Browser Windows or Tabs

 this.driver.Navigate().GoToUrl(@"http://automatetheplanet.com/compelling-sunday-14022016/");
    driver.FindElement(By.LinkText("10 Advanced WebDriver Tips and Tricks Part 1")).Click();
    driver.FindElement(By.LinkText("The Ultimate Guide To Unit Testing in ASP.NET MVC")).Click();
    ReadOnlyCollection<String> windowHandles = driver.WindowHandles;
    String firstTab = windowHandles.First();
    String lastTab = windowHandles.Last();
    driver.SwitchTo().Window(lastTab);
    Assert.AreEqual<string>("The Ultimate Guide To Unit Testing in ASP.NET MVC", driver.Title);
    driver.SwitchTo().Window(firstTab);
    Assert.AreEqual<string>("Compelling Sunday – 19 Posts on Programming and Quality Assurance", driver.Title);


//Navigation History
this.driver.Navigate().GoToUrl(
        @"http://www.codeproject.com/Articles/1078541/Advanced-WebDriver-Tips-and-Tricks-Part");
    this.driver.Navigate().GoToUrl(
        @"http://www.codeproject.com/Articles/1017816/Speed-up-Selenium-Tests-through-RAM-Facts-and-Myth");
    driver.Navigate().Back();
    Assert.AreEqual<string>(
        "10 Advanced WebDriver Tips and Tricks - Part 1 - CodeProject", 
        driver.Title);
    driver.Navigate().Refresh();
    Assert.AreEqual<string>(
        "10 Advanced WebDriver Tips and Tricks - Part 1 - CodeProject", 
        driver.Title);
    driver.Navigate().Forward();
    Assert.AreEqual<string>(
        "Speed up Selenium Tests through RAM Facts and Myths - CodeProject", 
        driver.Title);


//Change User Agent

FirefoxProfileManager profileManager = new FirefoxProfileManager();
FirefoxProfile profile = new FirefoxProfile();
profile.SetPreference(
"general.useragent.override",
"Mozilla/5.0 (BlackBerry; U; BlackBerry 9900; en) AppleWebKit/534.11+ (KHTML, like Gecko) Version/7.1.0.346 Mobile Safari/534.11+");
this.driver = new FirefoxDriver(profile);




//Set HTTP Proxy for Browser

FirefoxProfile firefoxProfile = new FirefoxProfile();
firefoxProfile.SetPreference("network.proxy.type", 1);
firefoxProfile.SetPreference("network.proxy.http", "myproxy.com");
firefoxProfile.SetPreference("network.proxy.http_port", 3239);
driver = new FirefoxDriver(firefoxProfile);


Handle SSL Certificate Error

//Handle SSL Certificate Error FirefoxDriver
FirefoxProfile firefoxProfile = new FirefoxProfile();
firefoxProfile.AcceptUntrustedCertificates = true;
firefoxProfile.AssumeUntrustedCertificateIssuer = false;
driver = new FirefoxDriver(firefoxProfile);


//Handle SSL Certificate Error ChromeDriver
DesiredCapabilities capability = DesiredCapabilities.Chrome();
Environment.SetEnvironmentVariable("webdriver.chrome.driver", "C:\\Path\\To\\ChromeDriver.exe");
capability.SetCapability(CapabilityType.AcceptSslCertificates, true);
driver = new RemoteWebDriver(capability);


//Handle SSL Certificate Error InternetExplorerDriver

DesiredCapabilities capability = DesiredCapabilities.InternetExplorer();
Environment.SetEnvironmentVariable("webdriver.ie.driver", "C:\\Path\\To\\IEDriver.exe");
capability.SetCapability(CapabilityType.AcceptSslCertificates, true);
driver = new RemoteWebDriver(capability);



//Scroll Focus to Control
this.driver.Navigate().GoToUrl(@"http://automatetheplanet.com/compelling-sunday-14022016/");
    IWebElement link = driver.FindElement(By.PartialLinkText("Previous post"));
    string jsToBeExecuted = string.Format("window.scroll(0, {0});", link.Location.Y);
    ((IJavaScriptExecutor)driver).ExecuteScript(jsToBeExecuted);
    link.Click();
    Assert.AreEqual<string>("10 Advanced WebDriver Tips and Tricks - Part 1", driver.Title);


//Focus on a Control

this.driver.Navigate().GoToUrl(
    @"http://automatetheplanet.com/compelling-sunday-14022016/");
    IWebElement link = driver.FindElement(By.PartialLinkText("Previous post"));

    //Option 1.
    link.SendKeys(string.Empty);

    //Option 2.
    ((IJavaScriptExecutor)driver).ExecuteScript("arguments[0].focus();", link);




1. Taking a Screenshot
public void TakeFullScreenshot(IWebDriver driver, String filename)
{
    Screenshot screenshot = ((ITakesScreenshot)driver).GetScreenshot();
    screenshot.SaveAsFile(filename, ImageFormat.Png);
}


public void TakeScreenshotOfElement(IWebDriver driver, By by, string fileName)
{
    // 1. Make screenshot of all screen
    var screenshotDriver = driver as ITakesScreenshot;
    Screenshot screenshot = screenshotDriver.GetScreenshot();
    var bmpScreen = new Bitmap(new MemoryStream(screenshot.AsByteArray));

    // 2. Get screenshot of specific element
    IWebElement element = driver.FindElement(by);
    var cropArea = new Rectangle(element.Location, element.Size);
    var bitmap = bmpScreen.Clone(cropArea, bmpScreen.PixelFormat);
    bitmap.Save(fileName);
}


[TestMethod]
public void WebDriverAdvancedUsage_TakingFullScrenenScreenshot()
{
    this.driver.Navigate().GoToUrl(@"http://automatetheplanet.com");
    this.WaitUntilLoaded();
    string tempFilePath = Path.GetTempFileName().Replace(".tmp", ".png");
    this.TakeFullScreenshot(this.driver, tempFilePath);
}

[TestMethod]
public void WebDriverAdvancedUsage_TakingElementScreenshot()
{
    this.driver.Navigate().GoToUrl(@"http://automatetheplanet.com");
    this.WaitUntilLoaded();
    string tempFilePath = Path.GetTempFileName().Replace(".tmp", ".png");
    this.TakeScreenshotOfElement(this.driver, 
    By.XPath("//*[@id='tve_editor']/div[2]/div[2]/div/div"), tempFilePath);
}



//Execute JavaScript
 this.driver.Navigate().GoToUrl(@"http://automatetheplanet.com");
    this.WaitUntilLoaded();
    IJavaScriptExecutor js = driver as IJavaScriptExecutor;
    string title = (string)js.ExecuteScript("return document.title");
    Debug.WriteLine(title);



//Set Page Load Timeout
this.driver.Manage().Timeouts().SetPageLoadTimeout(new TimeSpan(0, 0, 10));


private void WaitUntilLoaded()
{
    WebDriverWait wait = new WebDriverWait(driver, TimeSpan.FromSeconds(30));
    wait.Until((x) =>
    {
        return ((IJavaScriptExecutor)this.driver)
        .ExecuteScript("return document.readyState").Equals("complete");
    });
}



WebDriverWait wait = new WebDriverWait(driver, TimeSpan.FromSeconds(30));
wait.Until(ExpectedConditions.VisibilityOfAllElementsLocatedBy(
  By.XPath("//*[@id='tve_editor']/div[2]/div[2]/div/div")));



Execute Tests in a Headless Browser


this.driver = new PhantomJSDriver(
        @"D:\Projects\PatternsInAutomation.Tests\WebDriver.Series.Tests\Drivers");
    this.driver.Navigate().GoToUrl(@"http://automatetheplanet.com");
    this.WaitUntilLoaded();
    IJavaScriptExecutor js = driver as IJavaScriptExecutor;
    string title = (string)js.ExecuteScript("return document.title");
    Debug.WriteLine(title);



Check If an Element Is Visible
Assert.IsTrue(driver.FindElement(
        By.XPath("//*[@id='tve_editor']/div[2]/div[2]/div/div")).Displayed);



Use Specific Profile
FirefoxProfileManager profileManager = new FirefoxProfileManager();
FirefoxProfile profile = profileManager.GetProfile("YourProfileName");
this.driver = new FirefoxDriver(profile);



ChromeOptions options = new ChromeOptions();
// set some options
DesiredCapabilities dc = DesiredCapabilities.Chrome();
dc.SetCapability(ChromeOptions.Capability, options);
IWebDriver driver = new RemoteWebDriver(dc);



Turn Off JavaScript
FirefoxProfileManager profileManager = new FirefoxProfileManager();
FirefoxProfile profile = profileManager.GetProfile("HARDDISKUSER");
profile.SetPreference("javascript.enabled", false);
this.driver = new FirefoxDriver(profile);



Manage Cookies


Cookie cookie = new Cookie("key", "value");
this.driver.Manage().Cookies.AddCookie(cookie);



Get All Cookies
var cookies = this.driver.Manage().Cookies.AllCookies;
foreach (var currentCookie in cookies)
{
    Debug.WriteLine(currentCookie.Value);
}


Delete a Cookie by Name
this.driver.Manage().Cookies.DeleteCookieNamed("CookieName");

Delete All Cookies
this.driver.Manage().Cookies.DeleteAllCookies();

Get a Cookie by Name
var myCookie = this.driver.Manage().Cookies.GetCookieNamed("CookieName");
Debug.WriteLine(myCookie.Value);


Maximize Window
driver.Manage().Window.Maximize();

```

## Select
```java
new Select(driver.findElement(By.id("gender"))).selectByVisibleText("Germany");


Select dropdown = new Select(driver.findElement(By.id("identifier")));
dropdown.selectByVisibleText("Programmer ");
dropdown.selectByIndex(1);
dropdown.selectByValue("prog");


WebElement select = driver.findElement(By.id("gender"));
List<WebElement> options = select.findElements(By.tagName("option"));



for (WebElement option : options) {

if("Germany".equals(option.getText().trim()))

 option.click();   
}



List<WebElement> list = sel.getOptions();
 for(int i=0;i<list.size();i++){
        if(list.get(i).getText().equals(sel.getFirstSelectedOption().getText())){
            System.out.println("The index of the selected option is: "+i);
            break;
            }


//checks whether the check box is selected or not. If it is not selected, then it selects.
if ( !driver.findElement(By.id("idOfTheElement")).isSelected() )
{
     driver.findElement(By.id("idOfTheElement")).click();
}


```


## Select
```java



//Start FirefoxDriver with Plugins
FirefoxProfile profile = new FirefoxProfile();
profile.AddExtension(@"C:\extensionsLocation\extension.xpi");
IWebDriver driver = new FirefoxDriver(profile);



//Set HTTP Proxy ChromeDriver
ChromeOptions options = new ChromeOptions();
var proxy = new Proxy();
proxy.Kind = ProxyKind.Manual;
proxy.IsAutoDetect = false;
proxy.HttpProxy =
proxy.SslProxy = "127.0.0.1:3239";
options.Proxy = proxy;
options.AddArgument("ignore-certificate-errors");
IWebDriver driver = new ChromeDriver(options);


//Set HTTP Proxy with Authentication ChromeDriver
ChromeOptions options = new ChromeOptions();
var proxy = new Proxy();
proxy.Kind = ProxyKind.Manual;
proxy.IsAutoDetect = false;
proxy.HttpProxy =
proxy.SslProxy = "127.0.0.1:3239";
options.Proxy = proxy;
options.AddArguments("--proxy-server=http://user:password@127.0.0.1:3239");
options.AddArgument("ignore-certificate-errors");
IWebDriver driver = new ChromeDriver(options);


Start ChromeDriver with an Unpacked Extension
ChromeOptions options = new ChromeOptions();
options.AddArguments("load-extension=/pathTo/extension");
DesiredCapabilities capabilities = new DesiredCapabilities();
capabilities.SetCapability(ChromeOptions.Capability, options);
DesiredCapabilities dc = DesiredCapabilities.Chrome();
dc.SetCapability(ChromeOptions.Capability, options);
IWebDriver driver = new RemoteWebDriver(dc);


//Start ChromeDriver with an Packed Extension
ChromeOptions options = new ChromeOptions();
options.AddExtension(Path.GetFullPath("local/path/to/extension.crx"));
DesiredCapabilities capabilities = new DesiredCapabilities();
capabilities.SetCapability(ChromeOptions.Capability, options);
DesiredCapabilities dc = DesiredCapabilities.Chrome();
dc.SetCapability(ChromeOptions.Capability, options);
IWebDriver driver = new RemoteWebDriver(dc);


//Assert a Button Enabled or Disabled

IWebElement button = driver.FindElement(By.XPath("/html/body/button"));
Assert.IsFalse(button.Enabled);



//Set and Assert the Value of a Hidden Field
////<input type="hidden" name="country" value="Bulgaria"/>
    IWebElement theHiddenElem = driver.FindElement(By.Name("country"));
    string hiddenFieldValue = theHiddenElem.GetAttribute("value");
    Assert.AreEqual("Bulgaria", hiddenFieldValue);
    ((IJavaScriptExecutor)driver).ExecuteScript(
        "arguments[0].value='Germany';",
        theHiddenElem);
    hiddenFieldValue = theHiddenElem.GetAttribute("value");
    Assert.AreEqual("Germany", hiddenFieldValue);



//Wait AJAX Call to Complete Using JQuery

public void WaitForAjaxComplete(int maxSeconds)
{
    bool isAjaxCallComplete = false;
    for (int i = 1; i <= maxSeconds; i++)
    {
        isAjaxCallComplete = (bool)((IJavaScriptExecutor)driver).
        ExecuteScript("return window.jQuery != undefined && jQuery.active == 0");

        if (isAjaxCallComplete)
        {
            return;
        }
        Thread.Sleep(1000);
    }
    throw new Exception(string.Format("Timed out after {0} seconds", maxSeconds));
}



//Verify File Downloaded ChromeDriver
[TestMethod]
public void VerifyFileDownloadChrome()
{
    string expectedFilePath = @"c:\temp\Testing_Framework_2015_3_1314_2_Free.exe";
    try
    {
        String downloadFolderPath = @"c:\temp\";
        var options = new ChromeOptions();
        options.AddUserProfilePreference("download.default_directory", downloadFolderPath);
        driver = new ChromeDriver(options);

        driver.Navigate().GoToUrl("https://www.telerik.com/download-trial-file/v2/telerik-testing-framework");
        WebDriverWait wait = new WebDriverWait(driver, TimeSpan.FromSeconds(30));
        wait.Until((x) =>
        {
            return File.Exists(expectedFilePath);
        });
        FileInfo fileInfo = new FileInfo(expectedFilePath);
        long fileSize = fileInfo.Length;
        Assert.AreEqual(4326192, fileSize);
    }
    finally
    {
        if (File.Exists(expectedFilePath))
        {
            File.Delete(expectedFilePath);
        }
    }
}


//Verify File Downloaded FirefoxDriver
public void VerifyFileDownloadFirefox()
{
    string expectedFilePath = @"c:\temp\Testing_Framework_2015_3_1314_2_Free.exe";
    try
    {
        String downloadFolderPath = @"c:\temp\";
        FirefoxProfile profile = new FirefoxProfile();
        profile.SetPreference("browser.download.folderList", 2);
        profile.SetPreference("browser.download.dir", downloadFolderPath);
        profile.SetPreference("browser.download.manager.alertOnEXEOpen", false);
        profile.SetPreference("browser.helperApps.neverAsk.saveToDisk", "application/msword, application/binary, application/ris, text/csv, image/png, application/pdf, text/html, text/plain, application/zip, application/x-zip, application/x-zip-compressed, application/download, application/octet-stream");
        this.driver = new FirefoxDriver(profile);

        driver.Navigate().GoToUrl("https://www.telerik.com/download-trial-file/v2/telerik-testing-framework");
        WebDriverWait wait = new WebDriverWait(driver, TimeSpan.FromSeconds(30));
        wait.Until((x) =>
        {
            return File.Exists(expectedFilePath);
        });
        FileInfo fileInfo = new FileInfo(expectedFilePath);
        long fileSize = fileInfo.Length;
        Assert.AreEqual(4326192, fileSize);
    }
    finally
    {
        if (File.Exists(expectedFilePath))
        {
            File.Delete(expectedFilePath);
        }
    }
}








```

## License


## Links		
* [Automate Telerik Kendo Grid Webdriver](http://automatetheplanet.com/automate-telerik-kendo-grid-webdriver/)




