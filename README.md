# Forecasting-Average-Monthly-TTF-Natural-Gas-Prices-in-Real-Time
This is the repository supporting the research "Forecasting Average Monthly TTF Natural Gas Prices in Real Time". It contains all the data and code.

Summary of the research it supports:
In my dissertation, I tested 27 variations of models and model-free techniques to forecast average monthly TTF natural gas prices in real time, across horizons from 1 to 24 months forward. Every model was held to a strict real-time constraint: only information available at the forecast origin was used, eliminating any look-ahead bias. I also tested multiple approaches of pooling forecasts together for improved accuracy.

Three findings stood out:
→ Simplicity wins. AR(12), a relatively simple autoregressive model using 12 monthly lags, outperformed all others from h=3 through h=24, achieving statistical significance over the random walk benchmark from 15 months forward. For 1-month forward forecasts, however, a random walk using the most recent end-of-month price was the best available tool.
→ VAR models, which incorporate storage levels, LNG import flows, and temperature, performed worst overall. The Russia-EU energy shock of 2021–2022 exposed their core weakness: when TTF prices detached from fundamentals entirely, the models built on those fundamentals failed catastrophically. AR(12), relying solely on price history, had no such relationship to break.
→ Forecast combinations, a technique shown to improve accuracy in the US natural gas market, failed to add value in the European market. When two conceptually similar models dominate, which is the case, combining them with weaker ones simply dilutes their performance accuracy.

An interesting pattern emerged beyond the main findings:
AR(12) and VAR(1) display performance complementarity - periods where one outperforms the benchmark consistently coincide with the other underperforming, and vice versa. This suggests a potential regime-switching framework where both models are used in tandem, with the active model determined by the prevailing market regime. Whether this complementarity is stable enough to be exploited in practice remains an open empirical question, but it is one worth testing.

Putting it in perspective:
Even the best-performing models deviated from realized prices by 50–63% in absolute terms. Despite relative outperformance over a globally accepted benchmark, forecastability remains elusive.


To see the full paper, see a post on my linkedin: (https://www.linkedin.com/feed/update/urn:li:activity:7467137881648709633/)

Navigation tips through repository:
Each of the files contains a Jupiter Notebook with the code and the Excel with the data required for running it.
"Combinations of Forecasts" pools all the individual forecasts together using 8 different approaches.
"Analysis (MSPE ratio table)" and "Analysis (24m rolling window)" are the 2 analytical files, which gather results and create visualisations for ease of interpretations.
The rest of the files are the models used for forecasting.
