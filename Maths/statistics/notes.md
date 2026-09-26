# Phase 1 — Statistics Notes

## Mean

Average of a dataset.
\[
\bar{x}=\frac{1}{n}\sum\_{i=1}^{n}x_i
\]
\(x_i\)=observation, \(n\)=sample size. ML: EDA, feature analysis, standardization.

## Median

Middle value after sorting. More resistant to outliers than mean. ML: robust data analysis.

## Mode

Most frequent value. ML: useful for categorical/frequency analysis.

## Population vs Sample

Population = entire group; sample = subset.
\[
\mu=\frac{1}{N}\sum*{i=1}^{N}x_i,\qquad
\bar{x}=\frac{1}{n}\sum*{i=1}^{n}x_i
\]
ML: datasets are samples from a broader real-world population.

## Sample Variance

\[
s^2=\frac{1}{n-1}\sum*{i=1}^{n}(x_i-\bar{x})^2
\]
Population:
\[
\sigma^2=\frac{1}{N}\sum*{i=1}^{N}(x_i-\mu)^2
\]
ML: measures spread; important for feature analysis and bias-variance.

## Standard Deviation

Square root of variance.
\[
\sigma=\sqrt{\sigma^2},\qquad s=\sqrt{s^2}
\]
Standardization:
\[
z=\frac{x-\mu}{\sigma}
\]
ML: puts features on comparable scales.

## Sampling

Selecting observations from a population. Common methods: random, stratified, systematic. ML: poor sampling can cause sampling bias and poor generalization.

## Confidence Interval

A range produced by a statistical procedure for estimating a population parameter.
\[
\bar{x}\pm z\frac{\sigma}{\sqrt n}
\]
\(\bar{x}\)=sample mean, \(z\)=critical value, \(\sigma\)=population SD, \(n\)=sample size. For a 95% normal-based interval, \(z\approx1.96\). ML: quantify uncertainty in evaluation estimates.

## Hypothesis Testing

Tests whether observed data are inconsistent with a specified null hypothesis.
\[
H_0=\text{null},\qquad H_1=\text{alternative}
\]
p-value = probability, assuming \(H_0\) is true, of observing a test statistic at least as extreme as the one obtained. If \(p<0.05\), often reject \(H_0\) at a preselected 5% level. ML: A/B tests and model comparisons.

## Correlation

Strength and direction of linear association.
\[
r=\frac{Cov(X,Y)}{\sigma_X\sigma_Y},\qquad -1\le r\le1
\]
ML: feature analysis and redundancy detection. Correlation does not imply causation.

## Covariance

How two variables change together.
\[
Cov(X,Y)=E[(X-E[X])(Y-E[Y])]
\]
Positive = move together; negative = opposite movement. ML: covariance matrices and PCA.

## Bias–Variance

Bias = error from overly simple assumptions → underfitting. Variance = sensitivity to training data → overfitting.
\[
Expected\ Error\approx Bias^2+Variance+Irreducible\ Noise
\]
ML: explains generalization and model complexity.

## Generalization

How well a model performs on unseen data from the target distribution. ML goal: learn transferable patterns rather than memorize training data.

## AI Engineering Connection

```text
Raw Data → Sampling → EDA → Statistics → Feature Analysis
→ Training → Evaluation → Uncertainty/Testing → Generalization
```

For GenAI: evaluate retrieval quality, RAG accuracy, hallucination rates, latency distributions, A/B experiments, model comparisons, and production metrics.
