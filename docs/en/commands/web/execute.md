# Execute Script

Inject a snippet of JavaScript into the page for execution in the context of the currently selected frame (Web context only)
## Example Usage

```java
// Java
((JavascriptExecutor) driver).executeScript("window.setTimeout(arguments[arguments.length - 1], 500);");

```

```python
# Python
self.driver.execute_script(‘document.title’)

```

```javascript
// Javascript
// webdriver.io example
var result = browser.execute(function(a, b, c, d) {
  // browser context - you may not access client or console
  return a + b + c + d;
}, 1, 2, 3, 4)

// node.js context - client and console are available
console.log(result.value); // outputs: 10



// wd example
await driver.safeAsync('document.title');

```

```ruby
# Ruby
@driver.execute_script("document.title")

```

```php
# PHP
// TODO PHP sample

```

```csharp
// C#
// TODO C# sample

```


## Description

The executed script is assumed to be synchronous and the result of evaluating the script is returned to the client.

The script argument defines the script to execute in the form of a function body. The value returned by that function will be returned to the client. The function will be invoked with the provided args array and the values may be accessed via the arguments object in the order specified.

Arguments may be any JSON-primitive, array, or JSON object. JSON objects that define a WebElement reference will be converted to the corresponding DOM element. Likewise, any WebElements in the script result will be returned to the client as WebElement JSON objects.


## Support

### Appium Server

|Platform|Driver|Platform Versions|Appium Version|Driver Version|
|--------|----------------|------|--------------|--------------|
| iOS | [XCUITest](/docs/en/drivers/ios-xcuitest.md) | None | None | None |
|  | [UIAutomation](/docs/en/drivers/ios-uiautomation.md) | None | None | None |
| Android | [UiAutomator2](/docs/en/drivers/android-uiautomator2.md) | None | None | None |
|  | [UiAutomator](/docs/en/drivers/android-uiautomator.md) | None | None | None |
| Mac | [Mac](/docs/en/drivers/mac.md) | None | None | None |
| Windows | [Windows](/docs/en/drivers/windows.md) | None | None | None |

### Appium Clients

|Language|Support|Documentation|
|--------|-------|-------------|
|[Java](https://github.com/appium/java-client/releases/latest)| None |  [seleniumhq.github.io](https://seleniumhq.github.io/selenium/docs/api/java/org/openqa/selenium/remote/RemoteWebDriver.html#executeScript-java.lang.String-java.lang.Object...-)  |
|[Python](https://github.com/appium/python-client/releases/latest)| None |  [selenium-python.readthedocs.io](http://selenium-python.readthedocs.io/api.html#selenium.webdriver.remote.webdriver.WebDriver.execute_script)  |
|[Javascript (WebdriverIO)](http://webdriver.io/index.html)| None |  [webdriver.io](http://webdriver.io/api/protocol/execute.html)  |
|[Javascript (WD)](https://github.com/admc/wd/releases/latest)| None |  [github.com](https://github.com/admc/wd/blob/master/lib/commands.js#L102)  |
|[Ruby](https://github.com/appium/ruby_lib/releases/latest)| None |  [www.rubydoc.info](http://www.rubydoc.info/gems/selenium-webdriver/Selenium/WebDriver/Driver:execute_script)  |
|[PHP](https://github.com/appium/php-client/releases/latest)| None |  [github.com](https://github.com/appium/php-client/)  |
|[C#](https://github.com/appium/appium-dotnet-driver/releases/latest)| None |  [github.com](https://github.com/appium/appium-dotnet-driver/)  |

## HTTP API Specifications

### Endpoint

`GET /wd/hub/session/:session_id/execute_async`

### URL Parameters

|name|description|
|----|-----------|
|session_id|ID of the session to route the command to|

### JSON Parameters

|name|type|description|
|----|----|-----------|
| script | `string` | The script to execute |
| args | `array` | The script arguments |

### Response

The script result (`any`)

## See Also

* [W3C Specification](https://www.w3.org/TR/webdriver/#dfn-execute-script)
* [JSONWP Specification](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidexecute_async)