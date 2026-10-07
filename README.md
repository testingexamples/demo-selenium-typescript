# Demo Selenium TypeScript

Demonstration of:

* [Selenium](https://www.selenium.dev/) browser automation testing
* [TypeScript](https://en.wikipedia.org/wiki/TypeScript) programming language
* [Node](https://nodejs.org/) runtime built on Chrome's V8 JavaScript engine
* [ChromeDriver](https://developer.chrome.com/docs/chromedriver) extends WebDriver by adding Chromium-specific capabilities

The exact scenario this demo walks through is specified in [spec/index.md](spec/index.md); the code and the spec must agree.

Many more examples are here:

* [SeleniumHQ examples](https://github.com/SeleniumHQ/seleniumhq.github.io/tree/trunk/examples)

## Install

### Install Node and NPM

Install Node and NPM from <https://nodejs.org/>

Run this to confirm your version:

```sh
node -v
```

Output should be at least:

```stdout
v23.6.1
```

Run this to confirm your version:

```sh
npm -v
```

Output should be at least:

```stdout
11.2.0
```

### Install TypeScript

Install TypeScript, ts-node, and Node type definitions:

```sh
npm install --save-dev typescript @types/node ts-node
```

### Install Selenium

Install Selenium WebDriver:

```sh
npm install --save selenium-webdriver@latest
```

Selenium WebDriver ships its own JavaScript implementation but does not
ship complete TypeScript type declarations, so also install the community
types package as a dev dependency:

```sh
npm install --save-dev @types/selenium-webdriver@latest
```

### Install chromedriver

Install Google chromedriver:

```sh
npm install --save chromedriver@latest
```

### Update

Run:

```sh
npm install npm@latest
npm upgrade
npm audit fix
```

## Run

Run:

```sh
./src/demo.ts
```

If you prefer, you can run with ts-node explicitly:

```sh
npx ts-node ./src/demo.ts
```

Or compile and run:

```sh
npx tsc ./src/demo.ts
node ./src/demo.js
```

The script will do three things:

1. Launch your local Chrome web browser to view the free open source testing examples web page <https://testingexamples.github.io/en-001/practice/>.

2. Interact with the web page in various ways, such as finding elements, clicking on elements, filling in form inputs, etc.

3. Print some typical HTML tag output that demonstrates the program is running successfully.

### Troubleshooting “chromedriver” Not Opened

If you get this kind of error message:

```txt
“chromedriver” Not Opened. Apple could not verify “chromedriver”
is free of malware that may harm your Mac or compromise your privacy.
```

Or this kind of error message:

```txt
Apple is not able to verify that it is free from malware that could harm your
Mac or compromise your privacy. Don’t open this unless you are certain it is
from a trustworthy source.
```

Then click "Done".

Try this command line solution:

```sh
xattr -d com.apple.quarantine $(which chromedriver) 2>/dev/null
```

Try adjusting your system settings:

* Apple menu -> Settings -> Security & Privacy -> General

* See the entry that says: "chromedriver" was blocked to protect your Mac.

* Click the button "Allow Anyway".

### Troubleshooting "This version of ChromeDriver …"

If you get this kind of error message:

```txt
UnhandledPromiseRejectionWarning:
SessionNotCreatedError: session not created:
This version of ChromeDriver only supports Chrome version …
```

Then you may need to harmonize your Chrome browser app and your Chrome webdriver.

If you use macOS brew, then upgrade chromedriver:

```sh
brew upgrade chromedriver
```

To update your Chrome browser app:

* On your computer, open Chrome.

* Find your current Chrome version by typing in the URL bar: `chrome://version/`.

* You should see a web page with many details, and you should see the first line with the version number, such as: "Google Chrome 135.0.7049.86 (Official Build)".

* At top right, tap the "More" icon, which is 3 vertical dots.

* You see the "More" menu. If you see a menu item "Update", then choose it. If you don't see a menu item "Update", then  you're on the current version.

To update your Chrome webdriver:

* Go to https://chromedriver.chromium.org/downloads

* Download the version that matches your Chrome browser app.

## Tracking

* Package: demo-selenium-typescript
* Version: 1.0.0
* Created: 2026-09-03T00:00:00Z
* Updated: 2026-09-03T00:00:00Z
* License: GPL-2.0-or-greater or for custom license contact us
* Contact: Joel Parker Henderson (joel@joelparkerhenderson.com)
