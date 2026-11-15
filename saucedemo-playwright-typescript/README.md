# SauceDemo E-Commerce UI Automation | Playwright + TypeScript

An end-to-end UI automation project for the SauceDemo demo e-commerce application. It uses Playwright Test with TypeScript, Page Object Model (POM), reusable test data, HTML reporting, and GitHub Actions CI.

## Tech stack

- TypeScript
- Playwright Test
- Node.js
- Page Object Model (POM)
- GitHub Actions
- HTML test report

## Scenarios covered

| Area | Test scenarios |
|---|---|
| Login | Successful login, locked-out user, invalid credentials, empty username validation |
| Products | Product listing availability, price sorting |
| Cart | Add product, verify cart item, remove product, empty-cart verification |
| Checkout | Complete purchase journey, required first-name validation |
| CI | Automated test execution on push and pull request |

## Project structure

```text
saucedemo-playwright-typescript/
├── .github/
│   └── workflows/
│       └── playwright.yml
├── pages/
│   ├── CartPage.ts
│   ├── CheckoutPage.ts
│   ├── InventoryPage.ts
│   └── LoginPage.ts
├── tests/
│   ├── cart.spec.ts
│   ├── checkout.spec.ts
│   └── login.spec.ts
├── utils/
│   └── test-data.ts
├── .env.example
├── .gitignore
├── package.json
├── playwright.config.ts
├── tsconfig.json
└── README.md
```

## Prerequisites

Install:
- Node.js 20 or later
- npm
- Git

Check installation:

```bash
node --version
npm --version
```

## Setup

Clone your repository, then run:

```bash
npm install
npx playwright install chromium
```

## Run tests

Run all tests:

```bash
npm test
```

Run with the browser visible:

```bash
npm run test:headed
```

Open Playwright UI mode:

```bash
npm run test:ui
```

Run smoke tests only:

```bash
npm run test:smoke
```

Run regression tests only:

```bash
npm run test:regression
```

View the HTML report:

```bash
npm run report
```

## Test credentials

The project uses the public SauceDemo demo credentials:

- Standard user: `standard_user`
- Password: `secret_sauce`
- Locked-out user: `locked_out_user`

These are demo-site credentials, not personal credentials.

## Configuration

The default base URL is `https://www.saucedemo.com`. To override it, set the `BASE_URL` environment variable.

PowerShell:

```powershell
$env:BASE_URL="https://www.saucedemo.com"
npm test
```

## Framework design

- **Page Object Model:** Page-specific locators and actions are maintained in separate page classes.
- **Reusable test data:** User credentials and product names are centralized in `utils/test-data.ts`.
- **Playwright assertions:** Uses auto-waiting web-first assertions.
- **Failure diagnostics:** Captures screenshots on failure, retains video on failure, and records traces on retry.
- **CI integration:** GitHub Actions runs the suite on pushes and pull requests and uploads the HTML report.

## GitHub Actions

The workflow is located at `.github/workflows/playwright.yml`. It installs Node.js dependencies and Chromium, executes the tests, and uploads the report as an artifact.

## Suggested future enhancements

- Add Firefox and WebKit browser projects.
- Add API tests and UI/API test integration.
- Add environment-based configuration for QA/staging.
- Add Allure reporting.
- Add accessibility checks.
- Add test data setup and teardown through API requests.

## Application under test

[ SauceDemo ](https://www.saucedemo.com)

---

**Portfolio note:** This repository demonstrates TypeScript-based browser automation, reusable POM architecture, end-to-end checkout validation, negative testing, test reporting, and CI pipeline integration.
