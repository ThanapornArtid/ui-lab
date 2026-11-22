# ui-lab

Automated UI tests for ITCS386. Tool parts that I chose: Part 3 Robot Framework and Part 4 Cypress. Both automate test case QP-01 on QuickPizza.

## robot

Robot Framework tests for Selenium's web form and QP-01. The keywords and locators for QuickPizza are in resources/quickpizza.resource, and results/run1 and results/run2 hold the logs and screenshots of two full runs.

    cd robot
    python3 -m venv .venv
    source .venv/bin/activate
    pip install -r requirements.txt
    robot -d results/run1 -v BROWSER:headlesschrome pizza_scenario.robot

Needs the CHROMEDRIVER environment variable to point to a ChromeDriver that matches your Chrome.

## cypress

Cypress specs for Selenium's web form and QP-01, with the admin login as a custom command in cypress/support/commands.js. The folders cypress/videos and cypress/screenshots hold the evidence of a full run.

    cd cypress
    npm install
    npx cypress run --browser chrome