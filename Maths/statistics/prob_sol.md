# Phase 1 — Statistics Practice Problems & Solutions

## Q1. Mean

Given [10,20,30,40,50]:
\[
\bar{x}=\frac{10+20+30+40+50}{5}=\frac{150}{5}=\boxed{30}
\]

## Q2. Median and Outlier

Given [10,12,13,15,100]:
\[
\bar{x}=\frac{150}{5}=\boxed{30}
\]
Middle value:
\[
\boxed{Median=13}
\]
Outlier:
\[
\boxed{100}
\]
Median is more resistant to the outlier.

## Q3. Population Variance

Data: [2,4,6].
\[
\mu=\frac{2+4+6}{3}=4
\]
\[
\sigma^2=\frac{(2-4)^2+(4-4)^2+(6-4)^2}{3}
=\frac{4+0+4}{3}
=\boxed{\frac83\approx2.667}
\]

## Q4. Standard Deviation

\[
\sigma=\sqrt{\sigma^2}=\boxed{\sqrt{\frac83}\approx1.633}
\]

## Q5. Population vs Sample

10,000 employees = \(\boxed{Population}\).
500 selected employees = \(\boxed{Sample}\).

## Q6. Standardization

Given \(x=80,\mu=70,\sigma=5\):
\[
z=\frac{x-\mu}{\sigma}=\frac{80-70}{5}=\boxed{2}
\]
The value is 2 SD above the mean.

## Q7. 95% Confidence Interval

Given \(\bar{x}=100,\sigma=20,n=100\):
\[
\bar{x}\pm1.96\frac{\sigma}{\sqrt n}
=100\pm1.96\frac{20}{10}
=100\pm3.92
\]
\[
\boxed{(96.08,103.92)}
\]

## Q8. Hypothesis Testing

Given \(p=0.03\), \(\alpha=0.05\).
\[
0.03<0.05
\]
Therefore:
\[
\boxed{\text{Reject }H_0}
\]
This means the result is statistically significant at the 5% level under the test assumptions; it does not mean the alternative has 97% probability of being true.

## Q9. Correlation

Given \(r=0.92\):
\[
\boxed{\text{Strong positive linear association}}
\]
Correlation does not imply causation.

## Q10. Bias

A simple model performs poorly on both training and validation data.
\[
\boxed{\text{High Bias}\rightarrow\text{Underfitting}}
\]

## Q11. Variance

Training accuracy = 99%, validation accuracy = 72%.
Large train/validation gap:
\[
\boxed{\text{High Variance}\rightarrow\text{Overfitting}}
\]

## Q12. RAG Evaluation

System A = 85%, System B = 87%.

Difference:
\[
87\%-85\%=2\text{ percentage points}
\]

A point estimate alone is insufficient. Check:

1. Sample size.
2. Uncertainty.
3. Confidence intervals.
4. Statistical testing.
5. Whether both systems used the same evaluation examples.
6. Practical significance.

Conceptual flow:

```text
Evaluation Dataset → Metric → Estimate → Uncertainty
→ Statistical Comparison → Practical Significance → Engineering Decision
```

## Final Answers

| Q   | Answer                                                                         |
| --- | ------------------------------------------------------------------------------ |
| Q1  | Mean = 30                                                                      |
| Q2  | Mean = 30, Median = 13, Outlier = 100                                          |
| Q3  | Variance = 8/3 ≈ 2.667                                                         |
| Q4  | SD = sqrt(8/3) ≈ 1.633                                                         |
| Q5  | Population = 10,000; Sample = 500                                              |
| Q6  | z = 2                                                                          |
| Q7  | 95% CI = (96.08, 103.92)                                                       |
| Q8  | Reject H0                                                                      |
| Q9  | Strong positive linear association                                             |
| Q10 | High bias → underfitting                                                       |
| Q11 | High variance → overfitting                                                    |
| Q12 | Need uncertainty, sample size, statistical testing, and practical significance |
