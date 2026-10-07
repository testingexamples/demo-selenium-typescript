# Agent instructions: demo-selenium-typescript

Demo Selenium TypeScript is a small beginner walkthrough script that uses
Selenium WebDriver (with ChromeDriver) and TypeScript to demonstrate
locating elements on https://testingexamples.github.io/en-001/practice/ by id, name, class
name, link text, and XPath, then filling a text input, checking a
checkbox, checking a radio button, and selecting an option from a
dropdown. This repo is not NHS-Wales-specific and not Google-specific —
it's the same generic testingexamples.github.io locator walkthrough as the
other demo repos in this collection (see `demo-selenium-javascript`, the
JavaScript source this repo was ported from, and
`demo-playwright-typescript`, the sibling this repo's TypeScript/tsconfig
conventions were adapted from).

`spec/index.md` is the single source of truth for the exact scenario this
demo walks through: the target URL, every locator used, and the expected
values. If the code in `src/demo.ts` and `spec/index.md` ever disagree,
that is a defect in one of them — fix it before doing anything else.

For how to install dependencies and run the script, see the Install and Run
sections in `README.md` rather than duplicating those steps here.

Non-negotiable: this repo is a walkthrough script, not a test suite. It
uses `console.log` to show what it found, not assertions (the lone
`assert(true)` near the top is a leftover no-op, not a real check). Do not
add strict pass/fail assertions or convert this into a test framework —
that would change what the demo is for. (For real assertion-based test
suites, see the sibling repos `demo-selenium-typescript-for-google-search`
and `demo-selenium-typescript-for-google-maps`.)

CLAUDE.md is a pointer to this file — it is the single source of truth for
agent instructions.
