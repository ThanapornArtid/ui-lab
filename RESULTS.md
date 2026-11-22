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
| 3    | Showed  Lab pizza 20261122 ,Scissors ,450 calories per slice | Pass |
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
- Step 4.3, failure message for the wrong title:
- Step 4.6, tool and calories in the answer of POST /api/pizza:
- Step 4.7, the line of the admin list that shows your pizza:
- Step 4.8, run 1, result, duration and pizza name:
- Step 4.8, run 2, result, duration and pizza name:
- Step 4.9 (optional), browser and result:

## Part B

1.
2.
3.
4.
5.
6.
7.