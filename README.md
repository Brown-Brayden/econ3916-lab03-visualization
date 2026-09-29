# econ3916-lab03-visualization
# Honest vs. Misleading Visualizations

## Objective

This project quantifies how design choices such as axis truncation, baseline selection, and inflation adjustment distort the message a chart conveys, and it establishes a reproducible exploratory data analysis (EDA) workflow for producing visualizations that faithfully represent the underlying data.

## Methodology

- **Summary statistics vs. visual inspection:** Reconstructed Anscombe's Quartet, four datasets with nearly identical means, variances, correlation coefficients (r ≈ 0.816), and fitted regression lines (ŷ ≈ 3 + 0.5x) but very different distributions. This showed that summary statistics alone cannot characterize a dataset.
- **Measuring distortion:** Applied Tufte's Lie Factor (the size of an effect shown in the graphic divided by the size of the effect in the data) to a revenue chart with a truncated y-axis, then redesigned it with a zero baseline and proportional encoding.
- **Framing effects in economic time series:** Plotted real average hourly earnings for production and nonsupervisory employees (FRED series AHETPI, deflated to constant 2020 dollars) under four presentation choices. The variations covered time window, axis scaling, baseline, and nominal vs. real values. Each choice produced a different narrative from the same data.
- **Structured EDA:** Ran a four-stage EDA checklist on World Bank GDP data covering 262 countries and aggregates from 1960 to 2023:
  1. *Structure:* dimensions, data types, coverage, and missingness
  2. *Distributions:* skewness and the need for log transformation
  3. *Relationships:* cross-sectional and temporal patterns
  4. *Anomalies:* outliers, structural breaks, and aggregate-region entries mixed in with sovereign states
- **Interactive diagnostics:** Built an interactive chart toggler that switches between honest and misleading design settings and recomputes the Lie Factor in real time, so viewers can see how each choice distorts the chart.

## Key Findings

- **Summary statistics are necessary but not sufficient.** Anscombe's Quartet confirms that datasets with the same first- and second-order moments can have linear, curved, outlier-driven, or leverage-dominated structures. Visual inspection is required before any statistical inference.
- **Axis truncation causes severe distortion.** The truncated revenue chart had a Lie Factor of 49, meaning the visual effect was 49 times larger than the actual change. Tufte's acceptable range is roughly 0.95 to 1.05. The redesigned chart brought the ratio back within that range.
- **Framing drives the narrative.** The four AHETPI charts showed that one real-wage series can support claims of stagnation, strong growth, volatility, or steady progress, depending only on the time window, scaling, and deflation choices. Analysts should state these choices and justify them explicitly.
- **Systematic EDA prevents analytical errors.** The World Bank dataset combines sovereign nations with regional and income-group aggregates and has uneven coverage across the 64-year span. Without a structured review, these issues can bias cross-country comparisons.
- **Interactivity builds visual literacy.** The live Lie Factor toggler turns distortion from an abstract idea into an observable effect. This makes it useful for teaching and for peer review of published charts.
