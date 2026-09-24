# A/B Test — ЖКХ Payment Form

## Executive Summary

This case study evaluates a new ЖКХ payment form designed to simplify the payment process through autofill.

The experiment compared the existing payment form (Control) with the new form (Test) and measured its impact on successful payment conversion.

**Key result:** the new form increased conversion from **65.7% to 80.4%**, an absolute uplift of **+14.7 percentage points** and a relative uplift of **+22.3%**.

The observed difference was statistically significant at the 5% significance level.

---

## Business Problem

The goal was to determine whether a redesigned ЖКХ payment form could increase the share of users who successfully complete a payment.

The new form introduced **autofill of payment details**, with the objective of reducing friction during the payment process.

The key product question was:

> Does the new payment form increase successful payment conversion compared with the existing form?

---

## Hypothesis

### Product hypothesis

Introducing autofill into the ЖКХ payment form will increase the conversion rate from opening the payment form to successfully completing a payment.

### Statistical hypotheses

**H₀:** Conversion in the new form is not higher than in the existing form.

**H₁:** Conversion in the new form is higher than in the existing form.

Significance level:

**α = 0.05**

---

## Experiment Design

| Parameter          | Description                                        |
| ------------------ | -------------------------------------------------- |
| Experiment period  | April 1–30, 2024                                   |
| Control group      | Existing payment form                              |
| Test group         | New payment form with autofill                     |
| Primary metric     | Conversion from form opening to successful payment |
| Statistical test   | One-sided z-test for two proportions               |
| Significance level | 0.05                                               |

### Conversion funnel

```text
Opened form
     ↓
Enter details
     ↓
Confirmation
     ↓
Successful payment
```

The analysis was performed at the **user level**.

A user was considered converted if at least one of their payments reached the final successful-payment step.

---

## Data Preparation

The analysis used two datasets:

* `Users`
* `Payments`

Before calculating the primary metric, the data was cleaned and validated.

Key steps included:

* removing isolated age outliers;
* handling records with missing city or experiment group;
* removing payments without a corresponding user ID;
* reconciling experiment group assignments after joining the datasets, with the user table used as the priority source;
* aggregating payment activity at the user level;
* checking the balance of the experiment groups.

---

## Key Metrics

| Metric                        | Control |         Test |
| ----------------------------- | ------: | -----------: |
| Successful payment conversion |   65.7% |    **80.4%** |
| Absolute uplift               |       — | **+14.7 pp** |
| Relative uplift               |       — |   **+22.3%** |

### Confidence interval

The 95% confidence interval for the conversion difference is:

**[10.2%; 19.1%]**

This indicates that the estimated uplift is positive across the entire confidence interval.

---

## Statistical Significance

A one-sided z-test for two proportions was used to test whether conversion in the Test group was higher than in the Control group.

**p-value ≈ 7.6 × 10⁻¹¹**

Since:

**p < 0.05**

the null hypothesis was rejected.

The difference in conversion between the two groups is statistically significant at the 5% significance level.

---

## Segment Analysis

The uplift was also examined across selected user segments.

### By device

| Device  | Control |  Test |       Uplift |
| ------- | ------: | ----: | -----------: |
| Android |   64.5% | 79.9% | **+15.4 pp** |
| iOS     |   67.2% | 80.8% | **+13.6 pp** |

### By city

| Segment       |       Uplift |
| ------------- | -----------: |
| Moscow        | **+18.2 pp** |
| St Petersburg | **+15.8 pp** |
| Regions       |  **+9.5 pp** |

The positive uplift was observed across all analyzed device and geographic segments.

---

## Product Recommendation

Based on the experiment results, the new payment form should be rolled out to all users.

The observed conversion uplift is both:

* **material from a product perspective** (+14.7 pp);
* **statistically significant** (p < 0.05).

After rollout, conversion should be monitored during the first week to confirm that the observed effect is maintained in the full user population.

---

## Methodology

The analysis included:

1. Data cleaning and validation
2. Dataset joining
3. Experiment group validation
4. User-level aggregation
5. Funnel analysis
6. Primary metric calculation
7. Statistical hypothesis testing
8. Confidence interval estimation
9. Segment analysis
10. Product recommendation

The detailed analysis and calculations are available in the Jupyter Notebook.

---

## Repository Structure

```text
ab-test-payment-form/
│
├── README.md
│
├── notebooks/
│   └── ab_test_analysis.ipynb
│
├── reports/
│   └── figures/
│       ├── funnel.png
│       ├── conversion_overall.png
│       ├── conversion_by_device.png
│       └── conversion_by_city.png
│
├── data/
│   └── README.md
│
├── requirements.txt
└── .gitignore
```

---

## Tools

* Python
* pandas
* NumPy
* SciPy
* Matplotlib
* Jupyter Notebook

---

## Project Focus

**Product Analytics · A/B Testing · Experimentation · Conversion Optimization · Statistical Analysis**
