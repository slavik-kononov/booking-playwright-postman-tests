Running tests
This project supports two types of automated tests:

1. Playwright booking tests
2. Postman API tests

The workflow can be started manually from GitHub Actions.

How to run:

GitHub → Actions → Automated Tests → Run workflow

Select one of the available options:
- playwright = Runs only Playwright booking tests
- postman = Runs only Postman API tests using Newman
- all = Runs both Playwright and Postman tests
Click Run workflow

Download Playwright Report:
1) Open the completed workflow run (Automated Tests - playwright or Automated Tests - all).
2) Scroll to the Artifacts section.
3) Download the artifact named: playwright-report-{run_number}
4) Extract the archive.
5) Open the report playwright-report-{index}/index.html in any browser.

Download Postman API tests:
1) Open the completed workflow run (Automated Tests - postman or Automated Tests - all).
2) Scroll to the Artifacts section.
3) Download the artifact named: postman-newman-report-{run_number}
4) Extract the archive.
5) Open the report postman-run-log.txt in Notepad or any text editor.


