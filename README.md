# Luka-PPG-Projection
A statistical projection of Luka Doncic's 2026-2027 NBA season PPG projection (using Bayesian Statistics)
# Luka Dončić 2026–27 PPG Projection

## Overview

This project develops a statistical projection of Luka Dončić's points per game (PPG) for the 2026–27 NBA season.

The objective is to estimate his expected end-of-season scoring average by combining historical performance with current-season observations. Rather than relying solely on his recent scoring average, the analysis incorporates Bayesian estimation, shooting efficiency, shot volume, and teammate lineup context.

## Methodology

The projection consists of four main components:

### 1. Bayesian Scoring Baseline

Historical scoring performance is combined with current-season observations using Bayesian shrinkage. This balances Luka's longer-term scoring tendencies against his more recent performance and reduces the influence of a relatively small sample.

### 2. Shooting Efficiency

Beta-Binomial models are used to estimate sustainable shooting percentages for:
- Two-point field goals
- Three-point field goals
- Free throws

Historical shooting percentages provide prior information, while current-season attempts and makes update the estimates.

### 3. Shot Volume

Historical and current-season attempt rates are combined to estimate future:
- Two-point attempts (2PA)
- Three-point attempts (3PA)
- Free-throw attempts (FTA)

These estimates are combined with projected shooting percentages using the scoring identity:

\[
PPG = 2(2PA)(2P\%) + 3(3PA)(3P\%) + FTA(FT\%)
\]

### 4. Teammate Lineup Analysis

Historical teammate On/Off data are used to examine how Luka's scoring rates differ depending on teammate availability on the court.

Teammates are classified into basketball archetypes, which inform prior distributions. Bayesian updating then combines these priors with current-season On/Off observations to estimate teammate-specific associations.

The resulting lineup adjustment is exploratory and descriptive rather than causal.

## Final Projection

The final projection combines the shooting-volume estimate with the estimated lineup-context adjustment.

The analysis distinguishes between the scoring baseline and the integrated projection rather than treating them as independent estimates to be added together.

## Repository Structure

- `Luka_data_analysis_clean.Rmd` — Reproducible R Markdown analysis.
- `Luka_Projection.pdf` — Rendered PDF containing the analysis and results.
- `data/` — Supporting datasets required for the analysis.

## Tools and Technologies

- **R** — Statistical analysis and modelling
- **R Markdown** — Reproducible reporting
- **hoopR** — NBA data retrieval
- **dplyr / tidyr / purrr** — Data manipulation
- **ggplot2** — Data visualization
- **Bayesian Statistics** — Parameter estimation and shrinkage

## Limitations

The projection is subject to several limitations:

- The current-season sample is relatively small.
- Shooting efficiency and shot volume may change over the remainder of the season.
- Injuries and playing-time changes may affect scoring output.
- Teammate On/Off observations are subject to confounding and overlapping playing time.
- Archetype classifications and prior distributions involve modelling assumptions.

Consequently, the lineup adjustment should not be interpreted as a causal effect of individual teammates on Luka's scoring.
