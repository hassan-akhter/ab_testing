# A/B Test Analysis — Landing Page Conversion Rate

This was my first end-to-end A/B testing project. I wanted to take something I had studied in my statistics course and actually apply it on a real messy dataset, because theory and practice feel completely different once you're dealing with 290K rows and mismatched data.


## What This Project Is About

A company ran an experiment — they showed some users their **old landing page** and others a **new landing page**, then tracked who converted (signed up / bought).

My job was to answer one question:

> **Is the new page actually better — or is the difference just random chance?**

## What I Did

- Cleaned 290,000+ rows - removed mismatched group assignments and duplicate users
- Compared conversion rates between control (old page) and treatment (new page)
- Ran a **two-proportion z-test** to test statistical significance
- Calculated a **95% confidence interval** to understand the range of the difference
- Ran a **power analysis** to confirm our sample was large enough to trust the result
- Visualised the results with matplotlib


## Key Finding

- Control Conversion Rate: 12.04%
- Treatment Conversion Rate: 11.88%
- Difference: 0.16% 
- Z-statistic: 1.3116
- P-value: 0.1897
- Standard Error: 0.0012
- 95% Confidence Interval: (−0.0008, 0.0039)
- Cohen's h : ~0.005
- Statistical Power: ≥ 0.80 

**Verdict: Do not launch the new page.**

The 0.16% difference is most likely random noise — not a genuine improvement. And thanks to the power analysis, I know this isn't a sample size problem. With 145K users per group we had more than enough to detect even a +0.5% lift.


## Tools & Libraries

- Python
- pandas
- numpy
- matplotlib
- statsmodels


## How To Run

1. Clone the repo
```bash
git clone https://github.com/hassan/ab-test-analysis.git
cd ab-test-analysis
```

2. Install dependencies
```bash
pip install -r requirements.txt
```

3. Add the dataset
   - Download `ABdata.csv` from [Kaggle A/B Testing Dataset](https://www.kaggle.com/datasets/zhangluyuan/ab-testing)
   - Place it in the root folder

4. Open the notebook
```bash
jupyter notebook testing_notebook.ipynb
```


## Project Structure

```
ab-test-analysis/
│
├── testing_notebook.ipynb       ← main analysis notebook
├── requirements.txt             ← dependencies
└── README.md                    ← you are here
```


## What I Would Do Next

- Build a logistic regression model to predict conversion probability
- Segment results by day of week to find timing patterns
- Rebuild visualisations in Plotly or Streamlit for interactivity
- Run the experiment for longer to catch smaller effects


## About Me

I'm Hassan, a student targeting Data roles. This project is part of my portfolio as I move from studying data concepts to actually applying them on real datasets.

Feel free to connect or give feedback — always looking to improve.
