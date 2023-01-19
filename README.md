<h1 align="center">Examining New Age Analytics of European Soccer</h1>
<p align="center"><strong>Analysis of team performance trends with regards to season outcomes</strong>

<h2>About</h2>

This was the group final project assigned in STAT 420: Methods of Applied Statistics during the Spring 2021 semester. The group members are listed in the [Credits section](https://github.com/benny-zhao/european-football-analytics/edit/main/README.md#credits).

We used a data set containing the four European Leagues during the 17-18, 18-19, and 19-20 seasons, which were the EPL, La Liga, Serie A, and Ligue 1. These are the highest levels of professional football in England, Spain, Italy, and France, respectively. The source of the data are as follows:

- France: [https://fbref.com/en/comps/13/history/Ligue-1-Seasons](https://fbref.com/en/comps/13/history/Ligue-1-Seasons)
- England: [https://fbref.com/en/comps/9/history/Premier-League-Seasons](https://fbref.com/en/comps/9/history/Premier-League-Seasons)
- Italy: [https://fbref.com/en/comps/11/history/Serie-A-Seasons](https://fbref.com/en/comps/11/history/Serie-A-Seasons)
- Spain: [https://fbref.com/en/comps/12/history/La-Liga-Seasons](https://fbref.com/en/comps/12/history/La-Liga-Seasons)

The data analysis was completed using R within RStudio involving the use of the following packages:

- From tidyverse: readr, ggplot2
- knitr
- faraway
- lmtest
- ggthemes

TeX was used for formatting the resulting report.

<h2>Objective</h2>

Our objective was to predict the success of a team, using the the proportion of games won as the metric, using variables like expected goals and the average player age.

This involved finding the optimal statistical model using a variety of methods listed below.

<h2>Methods</h2>

Our analysis involved the use of the following:

- Variable selection
- Collinearity analysis
- Linear regression
- Residual diagnostics
- Outlier diagnostics

<h2>Results</h2>

Based on our final model, we concluded that the proportion of games won by a team in a season were expected to increase as the expected goals, expected goals allowed, and the possesions as a proportion of attempted passes increased.

Conversely, the proportion of games won by a team in a season were expected to decrease if either their tier ranking was neither or if their tier ranking was Relegation spot.

More specifically, this model is represented as

$$\begin{matrix} y_{\text{W}_\text{Prop}}= -0.3565 + 0.005474x_{\text{xG}}+0.009628x_{\text{xGA}}+0.01340x_{\text{Poss}}-0.08358x_{\text{Neither}}-0.1703x_{\text{Relegation Spot}}-0.0002535x_{\text{xGA}}x_{\text{Poss}}\end{matrix}$$

- $y_{\text{W}_\text{Prop}}$ is the proportion of games won in a season
- $x_{\text{xG}}$ is the expected goals
- $x_{\text{xGA}}$ is the expected goals allowed
- $x_{\text{Poss}}$ is the possesions as a proportion of attempted passes
- $x_{\text{Neither}}$ is a binary variable: 1 if the tier ranking is neither, and 0 otherwise
- $x_{\text{Relegation Spot}}$ is a binary variable: 1 if the tier ranking is Relegation spot, and 0 otherwise

The adjusted $R^2$ value indicates that 86.597% of the variance in the proportion of games in a season is explained by our model, after adjusting for correlation due to random change.

Graphically, our model is visualized as the curved line in the following scatter plot, where teams are represented as green dots:

- The x-axis is the sum of the three positive terms in the model: expected goals $x_{\text{xG}}$, expected goals allowed $x_{\text{xGA}}$, and the possessions as a proportion of attempted passes $x_{\text{Poss}}$
- The y-axis is the proportion of games won by a team in a season

![Plot of Final Model](https://raw.githubusercontent.com/benny-zhao/european-football-analytics/main/finalModelScatterPlot.png)

<h2>Installation</h2>

1. Download this project as zip and extract it
2. Import it in RStudio

<h2>Credits</h2>

Group members:

- [Jefferson Mathews](mailto:jrm10@illinois.edu)
- [David Lin](mailto:yiyangl7@illinois.edu)
- [Vidushi Somani](mailto:vsomani3@illinois.edu)
- [Benny Zhao](mailto:bzhao22@illinois.edu)

Report formatting:

- Based on [Burak Ogan Mancarci's (University of British Columbia)](https://oganm.com/) [thesis proposal](https://github.com/oganm/ThesisProposal)
