# Booking Playwright + Postman Tests

## Running tests

This project supports two types of automated tests:

1. Playwright booking tests
2. Postman API tests

The tests can be started in two ways:

1. From GitHub Actions
2. Locally on your computer without GitHub Actions

---

## Run from GitHub Actions

The workflow can be started manually from GitHub Actions.

How to run:

1. Open the repository on GitHub.
2. Go to **Actions**.
3. Select **Automated Tests**.
4. Click **Run workflow**.
5. Select one of the available options:
   - `playwright` = Runs only Playwright booking tests
   - `postman` = Runs only Postman API tests using Newman
   - `all` = Runs both Playwright and Postman tests
6. Click **Run workflow**.

> Note: The **Run workflow** button is available only for users who have permission to run workflows in the repository. 
If a user does not see this button, they can run the tests locally using the instructions below.

---

## Run locally without GitHub Actions

Use this option if you do not have access to the **Run workflow** button in GitHub Actions, or if you want to run the tests on your own computer.

### 1. Install required software

Before running the project locally, install:

- Git
- Node.js
- npm

Check that they are installed:

```bash
git --version
node --version
npm --version
```

---

### 2. Download the project

You can download the project in one of two ways.

#### Option 1: Clone with Git

```bash
git clone https://github.com/slavik-kononov/booking-playwright-postman-tests.git
cd booking-playwright-postman-tests
```

#### Option 2: Download ZIP from GitHub

1. Open the repository on GitHub.
2. Click **Code**.
3. Click **Download ZIP**.
4. Extract the archive.
5. Open the extracted project folder in a terminal.

---

### 3. Install project dependencies

Run this command inside the project folder:

```bash
npm install
```

This command installs all packages from `package.json`.

---

## Run Playwright tests locally

### 1. Install Playwright browsers

Run this command once after installing dependencies:

```bash
npx playwright install
```

### 2. Run Playwright tests

```bash
npx playwright test
```

### 3. Open Playwright HTML report

After the test run, open the report with:

```bash
npx playwright show-report
```

If the report was generated as a folder, you can also open:

```text
playwright-report/index.html
```

in any browser.

---

## Run Postman API tests locally

Postman API tests are run through Newman.

### 1. Install dependencies

If Newman is already included in `package.json`, it will be installed by:

```bash
npm install
```

If Newman is not installed, install it manually:

```bash
npm install -D newman
```

### 2. Run Postman collection

Use the path to your Postman collection file:

```bash
npx newman run path/to/collection.json
```

Example:

```bash
npx newman run postman/collection.json
```

If the project uses an environment file, run:

```bash
npx newman run postman/collection.json -e postman/environment.json
```

---

## Run all tests locally

To run Playwright and Postman one after another:

```bash
npx playwright test
npx newman run postman/collection.json
```

If your project has scripts in `package.json`, you can use them instead, for example:

```bash
npm run playwright
npm run postman
npm run all
```

> Check the `scripts` section in `package.json` to see the exact available commands.

---

## Download Playwright Report from GitHub Actions

1. Open the completed workflow run:
   - **Automated Tests - playwright**
   - or **Automated Tests - all**
2. Scroll to the **Artifacts** section.
3. Download the artifact named:

```text
playwright-report-{run_number}
```

4. Extract the archive.
5. Open the report:

```text
playwright-report-{index}/index.html
```

in any browser.

---

## Download Postman API test report from GitHub Actions

1. Open the completed workflow run:
   - **Automated Tests - postman**
   - or **Automated Tests - all**
2. Scroll to the **Artifacts** section.
3. Download the artifact named:

```text
postman-newman-report-{run_number}
```

4. Extract the archive.
5. Open the report:

```text
postman-run-log.txt
```

in Notepad or any text editor.
