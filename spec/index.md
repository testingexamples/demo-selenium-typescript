# Spec: demo-selenium-typescript

## Summary

This spec describes the exact Selenium WebDriver walkthrough that
`src/demo.ts` performs against https://testingexamples.github.io/en-001/practice/.

## Scope

This spec covers the demo script's target site, every locator it uses, and
every form interaction it performs, so that the code and this document can
be checked against each other.

This spec does not cover installing Node, TypeScript, ts-node, Selenium, or
ChromeDriver, or troubleshooting driver/browser version mismatches — see
`README.md` for that.

## Principles and rules

* This is a walkthrough script, not a test suite. It demonstrates locator
  strategies and form interactions by printing HTML with `console.log`; it
  does not make assertions.
* The script targets exactly one page: https://testingexamples.github.io/en-001/practice/.
* `src/demo.ts` is a straight TypeScript port of `demo-selenium-javascript`'s
  `src/demo.js`, with explicit types (`WebDriver`, `WebElement`, `Select`,
  etc.) added throughout. The scenario, locators, and values are identical
  between the two; only the language and its type annotations differ.

## Detail

Target URL: `https://testingexamples.github.io/en-001/practice/`

Locators (verbatim from `src/demo.ts`):

1. `By.id("id-example-1")` — finds `<p id="id-example-1">Lorem Ipsum</p>`,
   demonstrates `By.id`.
2. `By.name("name-example-1")` — finds
   `<p name="name-example-1">Lorem Ipsum</p>`, demonstrates `By.name`.
3. `By.className("class-example-1")` — finds
   `<p class="class-example-1">Lorem Ipsum</p>`, demonstrates
   `By.className`.
4. `By.linkText("Link Example 1")` — finds
   `<a href="https://example.com">Link Example 1</a>`, demonstrates
   `By.linkText`.
5. `By.xpath("//input[@type='submit']")` — finds `<input type=submit>`,
   demonstrates `By.xpath`.

Form interactions (verbatim from `src/demo.ts`):

* Text input: `By.id("text-example-1-id")`, then `sendKeys("hello")`.
* Checkbox: `By.id("checkbox-example-1-id")`, then `click()`.
* Radio button: `By.id("radio-example-1-option-1-id")`, then `click()`.
* Select: `By.id("select-example-1-id")`, then
  `new Select(selectElement).selectByIndex(0)`, then
  `select.getFirstSelectedOption()`.

## Acceptance criteria

This demo still works when: the script completes without throwing, and
every locator resolves — each `findElement` call succeeds and each
`console.log` prints real `outerHTML` rather than an error.

## Related topics

* [../README.md](../README.md)
* [../AGENTS.md](../AGENTS.md)

## Sources

* <https://testingexamples.github.io/en-001/practice/>
