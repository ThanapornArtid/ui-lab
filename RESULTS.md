# UI lab results

Tool parts that I chose: Part 3 Robot Framework and Part 4 Cypress

## Part 0

- Step 0.1, Chrome version:157.0.8103.79 (Official Build) (arm64)
- Step 0.3, ChromeDriver version:157.0.8103.79
- Step 0.4, locator of Pizza, Please!:button[name="pizza-please"]
- Step 0.4, locator of Excluded tools:select
- Step 0.4, locator of Must be vegetarian:#default-checkbox
- Step 0.4, locator of Custom Pizza Name:input#pizza-name
- Step 0.5, pizza name, tool and calories of the run by hand: Lab pizza 20261122 (tool=Scissors, ingredients_number=6, Calories 450)

| Step | Actual result | Pass or fail |
|------|---------------|--------------|
| 1    | Looking to break out of your pizza routine? | Pass |
| 2    | Four advanced fields appeared | Pass |
| 3    | showed 600, Knife, vegetarian ticked and Lab Pizza 20261122 | Pass |
| 4    | Showed Lab Pizza 20261122, Tool: Scissors, 450 calories per slice | Pass |
| 5    | Please log in first | Pass |
| 6    | Showed "Latest pizza recommendations" | Pass |
| 7    | Showed my pizza name with tool=Scissors and ingredients_number| Pass |

## Part 3: Robot Framework

- robot --version: Robot Framework 7.5.1 (Python 3.14.5 on darwin)
- Step 3.2, failure message for the wrong title: Title should have been 'Web form Jaaa' but was 'Web form'.
- Step 3.8, run 1, result, elapsed time and pizza name:Pass,00:00:07.262,Lab Pizza 20261123
- Step 3.8, run 2, result, elapsed time and pizza name:Pass,00:00:06.731,Lab Pizza 20261123

## Part 4: Cypress

- node --version, npm --version and npx cypress version:
Cypress Version: 16.2.1 (stable)
System Platform: darwin (macOS - 26.6.2)
System Memory: 17.2 GB free 414 MB
Cypress package version: 16.2.1
Cypress binary version: 16.2.1
Electron version: 41.7.0
Bundled Node version: 24.15.0
- Step 4.3, failure message for the wrong title:  
Timed out retrying after 10000ms
      + expected - actual

      -'Web form'
      +'Web for jaaa'
- Step 4.6, tool and calories in the answer of POST /api/pizza:
tool: "Scissors"
calories: 575
- Step 4.7, the line of the admin list that shows your pizza:Lab Pizza 20261123-013015 (tool=Pizza cutter, ingredients_number=6) (newest)
- Step 4.8, run 1, result, duration and pizza name:All specs passed, 00:10, Lab Pizza 20261123-013303
- Step 4.8, run 2, result, duration and pizza name:All specs passed, 00:10, Lab Pizza 20261123-013526

## Part B

1. The three number boxes all use the id floating_filled, so $$("#floating_filled").length gave 3 and the id can't tell them apart. The page should give each box its own id like id="max-calories", so the test can use one short locator instead of depending on the label text.

2. Consistency oracle because it compares two outputs which is the tool on the home page and the tool in the admin list. It would catch a bug where the server saves a different tool than the one it showed.

3. QP-01 could check that every ingredient is vegetarian. The page only shows ingredient names, so the test needs the API answer from cy.intercept, which says "vegetarian": true and has a vegetarian field for each ingredient.

4. In Robot I had to write the waits myself, like Wait Until Element Contains and Wait Until The Page Is Ready but Cypress waited by itself for up to 10 seconds. Cypress was easier to set up because it does not need ChromeDriver. Robot runs took about 7 seconds and Cypress about 10 seconds for both specs. The Robot log shows every step with screenshots and Cypress video shows the whole run at once.

5. My group uses Selenium for Project 2, so I would choose Robot Framework, because SeleniumLibrary runs on Selenium WebDriver and ChromeDriver, the same setup as our project. Also, the resource file let me keep all QuickPizza locators in one place, so if QloApps changes a locator I only fix it once and the log.html with screenshots is a good evidence.

6. (Part 3) 
I would only change ${MAX CALORIES} in resources/quickpizza.resource. pizza_scenario.robot only calls keywords like Fill In The Pizza Request and never uses the locator, so the test file does not change.

7. (Part 4) 
Cypress clears the cookies before each test, and the cookie keeps the browser on one QuickPizza server.

If steps 6 and 7 were a second test, the browser could go to another server and my pizza might not be in the list.