# Eurojackpot statistical analysis

![PYTHON](https://img.shields.io/badge/Python-3.9.2-blue.svg)
[![GitHub Issues](https://img.shields.io/github/issues/mateuszschab/Eurojackpot-statistics.svg)](https://github.com/mateuszschab/Eurojackpot-statistics/issues)
![Contributions welcome](https://img.shields.io/badge/contributions-welcome-orange.svg)

## Basic Overview
Eurojackpot - a European numbers game that was established in March 2012. In 2022, 18 countries are participating in this lottery.
The script is only for statistical analysis and is not an incentive to play. All gambling involves risks. 

## Game rules
+ Players must select five main numbers between 1 and 50.

+ Players must select two extra Euro numbers between 1 and 12.

+ Players must purchase their tickets before the close of sales in their country before the draw takes place.

+ The jackpot has a cap of €120 million.

+ Draws are held every Tuesday and Friday in Helsinki, Finland, at 21.00 EET.

## Comments on the analysis
For the analysis of the analysis, you can use the current data, the source of which is included in the program, or plot the result.csv file (with data up to December 2022). It should be taken into account that the analysis covers the historical range from the beginning of the game's inception along with periods of rule changes. 
[The most important of these:](https://www.euro-jackpot.net/en/rules)
+ The Eurojackpot game rules have changed since the game began in 2012. Previously, the jackpot could not roll over more than 12 times, but this was found to be too limiting, and in February 2013 the rollover limit was removed and replaced with a Jackpot Cap of €90 million. The matrix for the Euro numbers has also changed, expanding from 1-8 to 1-10 in October 2014.

+ It was announced in early 2022 that the game would be updated with its biggest set of rule changes yet, with the addition of a Tuesday draw, the matrix for the Euro numbers expanding again from 1-10 to 1-12 and the jackpot cap going up to €120 million. The changes marked 10 years since Eurojackpot was launched in March 2012.

## Visualization of statistical results
+ Frequency of numbers in draws
![Example](https://github.com/mateuszschab/Eurojackpot-statistics/blob/main/img_project/number_freq_1.png)
+ Number of days since the last draw
![Example](https://github.com/mateuszschab/Eurojackpot-statistics/blob/main/img_project/number_freq_2.png)
+ Multiple draws of the same set of numbers
![Example](https://github.com/mateuszschab/Eurojackpot-statistics/blob/main/img_project/multi_draw_1.png)
+ Number of draws to reappear the same number (total)
![Example](https://github.com/mateuszschab/Eurojackpot-statistics/blob/main/img_project/redraw_single_number_1.png)
+ Frequency of the sum of the drawn numbers
![Example](https://github.com/mateuszschab/Eurojackpot-statistics/blob/main/img_project/sum_freq_1.png)
+ Proportion of even and odd numbers
![Example](https://github.com/mateuszschab/Eurojackpot-statistics/blob/main/img_project/even_odds_1.png)
+ Difference between numbers in draws
![Example](https://github.com/mateuszschab/Eurojackpot-statistics/blob/main/img_project/diff_number_freq_1.png)

## Random number generator

The program includes a number generator that generates a selected number of coupons and then tests on a selected one of the last draws. The total amount needed to buy coupons is returned, as well as the winnings according to the average winnings from all countries in December 2022.

The second generator is based on previously calculated data and includes in the criteria:
+ The number that has not been drawn for the longest time has an additional 5% to generate, while the most recently drawn has an additional 0%. The extra percentage for numbers in between is generated in a linear fashion.
+ The maximum difference between consecutive numbers does not exceed the 20th percentile of the history of previous draws.
+ The sum of the numbers is between the mean and +- the standard deviation from the historical data
+ The ratio of even and odd numbers remains within the 80th percentile

For each generator, a summary of the number of hits for each prize grade is created, as well as the total profit, or loss.
![Example](https://github.com/mateuszschab/Eurojackpot-statistics/blob/main/img_project/generator_result.png)

**Acknowledgements**
---
+ [Source of Historical Data Online](multipasko.pl)
+ [Information about the game, changes and statistics](https://www.euro-jackpot.net/en/how-to-play) (this is not the official website of the game)

