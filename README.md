[README.md](https://github.com/user-attachments/files/33314761/README.md)
# Experiment Design Audit — Power, Selection & Weighting

## Objective

I examined how experiment design and self-selection can lead to misleading conclusions, then checked how power analysis and weighting improve the analysis.

## Methodology

- Audited an A/B test that assigned 2% of traffic, or 1,000 users, to treatment.
- Calculated its power to detect a 0.8-percentage-point lift and the sample size needed for 80% power.
- Wrote a `power_check` function to compare the original allocation with an even split of the same 50,000 users.
- Identified baseline health as a confounder in a voluntary wellness-program comparison.
- Estimated propensity scores and used inverse probability weighting to adjust the comparison.

## Key Findings

The A/B test had only **19.8% power** to detect the target lift. An equal-sized design needed **12,514 users per group** for 80% power. This showed why the total number of users alone did not establish that the experiment was large enough.

The wellness program’s naive estimated effect was **−$1,396**, compared with the true effect of **−$500**. Healthier employees were more likely to participate and already had lower healthcare costs. After weighting, the estimated effect was **−$522**, much closer to the truth.
