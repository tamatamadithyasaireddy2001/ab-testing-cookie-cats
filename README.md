# ab-testing-cookie-cats
A/B test analysis of mobile game retention using Python and statistical hypothesis testing
# A/B Testing: Cookie Cats Mobile Game Retention Analysis

## Overview
Statistical analysis of an A/B test from the mobile game Cookie Cats, testing whether moving a gameplay gate from level 30 to level 40 affects player retention. Uses Python, pandas, and scipy for hypothesis testing on a real dataset of 90,189 players.

## Dataset
Cookie Cats mobile game A/B test data (public dataset, Kaggle) — 90,189 players randomly assigned to one of two groups:
- **gate_30** (control): gate placed at level 30
- **gate_40** (treatment): gate placed at level 40

Metrics: `sum_gamerounds`, `retention_1` (1-day retention), `retention_7` (7-day retention)

## Hypothesis
- **H0 (null):** Moving the gate from level 30 to level 40 has no effect on player retention.
- **H1 (alternative):** Moving the gate has a significant effect on player retention.

## Method
Used a chi-square test of independence to compare retention rates between the control (gate_30) and treatment (gate_40) groups, on both 1-day and 7-day retention.

## Results
| Metric | gate_30 | gate_40 | Chi-square | P-value | Significant? |
|---|---|---|---|---|---|
| 1-Day Retention | 44.8% | 44.2% | 3.16 | 0.0755 | No |
| 7-Day Retention | 19.0% | 18.2% | 9.96 | 0.0016 | Yes |

## Conclusion & Recommendation
No statistically significant difference was found in 1-day retention between the two groups. However, 7-day retention was significantly lower in the gate_40 group (p = 0.0016), suggesting the later gate placement may hurt longer-term player engagement.

**Recommendation:** Do not move the gate from level 30 to level 40. The data suggests the original placement (level 30) better supports long-term retention.

## Tools
Python, pandas, scipy.stats, matplotlib

## Notes
Personal project completed to practice A/B testing methodology and statistical hypothesis testing on a real-world dataset.
