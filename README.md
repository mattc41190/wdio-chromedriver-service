WDIO ChromeDriver Service
================================

(Based entirely on [wdio-selenium-standalone-service](https://github.com/webdriverio/wdio-selenium-standalone-service).)

----

This service helps you to run ChromeDriver seamlessly when running tests with the [WDIO testrunner](http://webdriver.io/guide/testrunner/gettingstarted.html). It uses the [chromedriver](https://www.npmjs.com/package/chromedriver) NPM package that wraps the ChromeDriver for you.

Note - this service does not require a Selenium server, but uses ChromeDriver to communicate with the browser directly.
Obvisously, it only supports:

```js
capabilities: [{
        browserName: 'chrome'
    }]
```

## Installation

The easiest way is to keep `wdio-chromedriver-service` as a devDependency in your `package.json`.

```json
{
  "devDependencies": {
    "wdio-chromedriver-service": "~0.1"
  }
}
```

You can simple do it by:

```bash
npm install wdio-chromedriver-service --save-dev
```

Note! You have to install [chromedriver](https://www.npmjs.com/package/chromedriver)  separately, as it's a peerDependency of this project, and you're free to choose what version to use. Install it using:

```bash
npm install chromedriver --save-dev
```

Instructions on how to install `WebdriverIO` can be found [here.](http://webdriver.io/guide/getstarted/install.html)

## Configuration

By design, only Google Chrome is available (when installed on the host system). In order to use the service you need to add `chromedriver` to your service array:

```js
// wdio.conf.js
export.config = {
  port: '9515',
  path: '/',
  // ...
  services: ['chromedriver'],
  chromeDriverArgs: ['--port=9999'],
  chromeDriverLogs: './',
  // ...
};
```

## Options

### chromeDriverArgs
Array of arguments to pass to the ChromeDriver executable, see [https://helpmanual.io/help/chromedriver](https://helpmanual.io/help/chromedriver).

Type: `string[]`
### chromeDriverLogs
Path where all logs from the ChromeDriver server should be stored.

Type: `string`



----

For more information on WebdriverIO see the [homepage](http://webdriver.io).
