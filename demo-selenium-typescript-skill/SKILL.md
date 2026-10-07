---
name: demo-selenium-typescript
description: Explains and adapts the demo-selenium-typescript Selenium WebDriver walkthrough (locating elements by id/name/class/link-text/xpath, filling a text input, checking a checkbox/radio, selecting a dropdown option) against https://testingexamples.github.io/en-001/practice/; invoke when asked to run, explain, extend, or port this demo, or to adapt it to a different site or Selenium version.
---

This skill covers the `demo-selenium-typescript` repo: a small TypeScript
script (`src/demo.ts`) that teaches Selenium WebDriver's locator strategies
(`By.id`, `By.name`, `By.className`, `By.linkText`, `By.xpath`) and basic
form interactions (filling a text input, checking a checkbox and radio,
selecting a dropdown option via `Select`) against the public demo site
https://testingexamples.github.io/en-001/practice/. This repo is a generic locator
walkthrough, not NHS-Wales-specific and not Google-specific. It is a
straight TypeScript port of the sibling repo `demo-selenium-javascript`,
typed using `@types/selenium-webdriver`, with the same tsconfig
conventions as the sibling repo `demo-playwright-typescript`.

To run it: install Node, npm, TypeScript/ts-node, Selenium WebDriver, and
chromedriver (see README.md's Install section), then run `./src/demo.ts`
or `npx ts-node ./src/demo.ts`. It launches a visible local Chrome window,
prints the outer HTML of each located element, fills in the form, and
quits.

To adapt this demo to a different site: change the URL passed to
`driver.get(...)` and update every locator to match the new site's markup,
then update `spec/index.md` to match — the spec and the code must always
agree. To adapt to a newer Selenium WebDriver version: update the
`selenium-webdriver`, `chromedriver`, and `@types/selenium-webdriver`
dependencies and re-check the `WebDriver`/`WebElement`/`By`/`Select` APIs
used here for breaking changes; the locator and interaction sequence
itself maps to Selenium's stable core API and is unlikely to need changes.

This skill summarizes the repo. `AGENTS.md` and `spec/index.md` are the
source of truth — if this skill's summary ever disagrees with those, they
win.
