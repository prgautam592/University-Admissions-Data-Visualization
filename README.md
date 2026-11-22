# Week 13 – University Admissions Data Visualization

**Course:** DSCI 505 – Fundamentals of Business Analytics
**University:** University of South Dakota
**Author:** Prakash Gautam

---

## Project Overview
This project uses Python data visualization to analyze university admissions data. Each visualization is created with three libraries (**Matplotlib, Seaborn, and Plotly**) so their syntax and features can be compared. The results are used to find patterns in application volume, test scores, and admission and enrollment outcomes, and to recommend strategies for admission and enrollment planning.

## Business Scenario
A university received **17,339 applications** across three colleges: **Business & Economics, Math & Science, and Arts & Letters**. The admissions office wants to understand how the colleges differ in application volume, academic performance, and admission outcomes. As a Business Data Analyst, my task is to analyze the data, find meaningful patterns, and recommend strategies to improve admission and enrollment planning.

## Dataset
**File:** `applications.xlsx` (17,339 rows)

| Column | Description |
|---|---|
| Applicant | Unique applicant identification number |
| Sex | Applicant's sex (M/F) |
| SAT_ACT | Standardized admission test score |
| College | College the applicant applied to |
| Admitted | Whether admission was offered (Yes/No) |
| Enrolled | Whether the applicant enrolled (Yes/No) |
| Extracurricular_Hours | Weekly hours spent on extracurricular activities |

## Tools and Libraries
- **Python 3**
- **pandas:** load, clean, group, and summarize the data
- **NumPy:** calculate the trendline for the Matplotlib scatter plot
- **Matplotlib:** basic static charts
- **Seaborn:** statistical charts with a cleaner default style
- **Plotly:** interactive charts (hover, zoom, pan)
- **statsmodels:** needed for Plotly's linear trendline

## Project Steps
1. **Load and explore the data:** `read_excel()`, `head()`, `shape`, `columns`, `dtypes`, `info()`
2. **Check for missing values:** `isnull().sum()` and `dropna()`
3. **Task 01 – Bar plot:** count applications by college with `groupby()` and compare them
4. **Task 02 – Histogram:** show the distribution of SAT/ACT scores
5. **Task 03 – Scatter plot:** plot SAT/ACT scores vs extracurricular hours with a linear trendline
6. **Task 04 – Insights:** use `map()` to turn Yes/No into 1/0, then calculate admission and yield rates by college

**Formulas used:**
- **Admission rate** = admitted ÷ applications × 100
- **Yield rate** = enrolled ÷ admitted × 100

## Results

### Task 01 – Applications by College
| College | Applications | Share |
|---|---|---|
| Arts & Letters | 6,964 | about 40% |
| Math & Science | 6,272 | about 36% |
| Business & Economics | 4,103 | about 24% |

**Arts & Letters attracts the most applicants.**

### Task 02 – Distribution of SAT/ACT Scores
Most applicants scored in the middle of the range, with fewer at the very low and very high ends.

### Task 03 – SAT/ACT vs Extracurricular Hours
The points form a wide cloud and the trendline is almost flat, so there is **no clear relationship** between SAT/ACT scores and extracurricular hours.

### Task 04 – Admission and Enrollment Summary
| College | Applications | Avg SAT/ACT | Admitted | Enrolled | Admission Rate | Yield Rate |
|---|---|---|---|---|---|---|
| Arts & Letters | 6,964 | 1,146.4 | 1,739 | 541 | 25.0% | 31.1% |
| Business & Economics | 4,103 | 1,173.6 | 1,470 | 499 | 35.8% | 33.9% |
| Math & Science | 6,272 | 1,178.9 | 2,114 | 488 | 33.7% | 23.1% |
| **Total** | **17,339** | | **5,323** | **1,528** | **30.7%** | **28.7%** |

## Key Findings
1. **Application demand is uneven across colleges.** Arts & Letters receives the most applications (about 40%) and has the lowest admission rate (25.0%). Business & Economics receives the fewest (about 24%).
2. **Admission is strongly linked to test scores.** Admitted applicants average 1,286.0 on the SAT/ACT compared with 1,110.8 for applicants who were not admitted, a gap of about 175 points.
3. **Extracurricular hours are not related to test scores, and yield differs by college.** The trendline is almost flat. Only 28.7% of admitted students enroll overall. Math & Science admits the most students (2,114) but has the lowest yield (23.1%), while Business & Economics has the highest yield (33.9%).

## Recommendations
1. **Match resources to demand.** Assign more reviewers to Arts & Letters, and run targeted recruitment (high-school visits, scholarships, program marketing) for Business & Economics.
2. **Use holistic review.** Because extracurricular hours are not tied to test scores, they could be considered as a separate factor in admission decisions to find strong applicants that scores alone would miss.
3. **Improve yield in Math & Science.** Follow up quickly with admitted students through admitted-student days, faculty and lab outreach, and competitive financial aid. Plan class sizes using each college's own yield rate rather than the university-wide rate of 28.7%.

## Comparing Matplotlib, Seaborn, and Plotly
| Feature | Matplotlib | Seaborn | Plotly |
|---|---|---|---|
| Level | Low-level, full control | High-level, built on Matplotlib | High-level, interactive |
| Syntax | More lines of code | Short, works directly with DataFrames | Short, works directly with DataFrames |
| Trendline | Calculated with `np.polyfit()`, then drawn | Built in with `regplot()` | Built in with `trendline='ols'` |
| Interactivity | Static | Static | Hover, zoom, pan |
| Best for | Custom, detailed charts | Quick statistical charts | Dashboards and presentations |

## Repository Structure
```
├── Week13_Admissions_Visualization.ipynb   # Full analysis with charts and comments
├── applications.xlsx                       # Dataset
├── requirements.txt                        # Python packages needed
└── README.md                               # Project summary
```

## How to Run
1. Clone this repository or download the files.
2. Install the required packages:
```
   pip install -r requirements.txt
```
3. Open the notebook:
```
   jupyter notebook Week13_Admissions_Visualization.ipynb
```
4. Keep `applications.xlsx` in the same folder as the notebook, then select **Kernel → Restart & Run All**.

> **Note:** GitHub's preview may not show the interactive Plotly charts. To see them, open the notebook in Jupyter, or paste the notebook's GitHub link into [nbviewer.org](https://nbviewer.org).

## Conclusion
All three libraries showed the same patterns in different ways. Matplotlib gives the most control, Seaborn makes statistical charts quickly, and Plotly creates interactive charts for stakeholders. The analysis shows that Arts & Letters has the highest application demand, test scores strongly affect admission, extracurricular hours are not related to test scores, and enrollment yield (especially in Math & Science) needs attention in planning.
