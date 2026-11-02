# Introduction to Programming – 001_PORT: Portfolio of work
**Customer Data Pre-processing** · Lecturer: Brian Tompsett · Individual · 80% of module

- **Due:** Tue 24 Nov 2026, 14:00 (available until 1 Dec 2026, 14:00 – late penalties apply after the due date)
- **Workload guidance:** 60–80 hours
- **Submit:** one ZIP file on Canvas containing the .ipynb notebook (with all output cells shown) plus every file it generates: processed.json, retired.json, employed.json, remove_ccard.json, commute.json and the saved seaborn plots.
- **Canvas:** https://canvas.hull.ac.uk/courses/79199/assignments/282460
- **Brief PDF:** https://canvas.hull.ac.uk/files/6967316/download?download_frd=1
- **Data (acw_user_data.csv):** https://canvas.hull.ac.uk/files/6967294/download?download_frd=1
- Use Jupyter (not VS Code or Colab), as the module asks.

## Background
A company exports its customer records only as a flat CSV (acw_user_data.csv). Prepare the data for colleagues: change representations, filter, and derive new attributes. Fields include names, credit card, marital status, car details and more. The solution must be programmatic and robust to varying data.

## Data Processing (70%) – standard Python only (os, sys, time, json, csv…; no pandas/seaborn)
1. Read the data with the `csv` library.
2. Convert flat columns into nested structures, casting values to the right types:
   - **Vehicle**: make, model, year, type
   - **Credit Card**: start date, end date, number, security code, IBAN
   - **Address**: main address, city, postcode
3. Fix empty dependants values (`" "` or `""`) with something meaningful, and print the rows corrected, e.g. `Problematic rows for dependants: [16, 58, 80, 98]`.
4. Write all records to **processed.json**: a list of dictionaries, one per person (format in the brief's appendix).
5. Write **retired.json** (retired field) and **employed.json** (employer field).
6. Write a function that takes one CSV row and flags it if the credit card start–end gap is over 10 years (dates are `MM/YY`). Write flagged people to **remove_ccard.json**.
7. From processed.json, add a **"Salary-Commute"** attribute = salary per km of commute (if commute ≤ 1 km, use salary). Sort ascending and save to **commute.json**.

## Data Visualisation (20%) – pandas + seaborn, reading the original CSV
1. Get the Salary and Age series; calculate **mean salary** and **median age**.
2. Univariate plots:
   - Age, working out how many bins give a bin width of 5
   - Dependants, fixing data errors with seaborn itself
   - Age (default bins) conditioned on marital status
3. Multivariate plots:
   - Commute distance vs salary
   - Age vs salary
   - Age vs salary conditioned by dependants
4. Add a notebook cell that saves the plots, run it, and include the images in the submission.

## Code Presentation (10%)
Clear structure, logic and comments; sensible variable names; no scope leakage; reusable functions with little duplication; error handling where appropriate; Markdown cells to separate tasks; docstrings for functions.

## Rubric highlights
- Data processing (70): top marks need every task error-free, all JSON outputs, correct casting with error handling, no unused variables, robust algorithms, minimal duplication and few repeated file opens/closes.
- Notebook use (10): good Markdown, docstrings, efficient and well-scoped code.
- Visualisation (20): all plots error-free, a save cell for each figure, good use of seaborn parameters for readability.

Weekly lab progress quizzes on Canvas can be used to check progress. Support continues through the Teams help channel.
