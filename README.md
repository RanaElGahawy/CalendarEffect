# Calendar Effects in Stock Market

## Quickstart

```bash
# clone project
git clone "https://github.com/epfl-ada/ada-2025-project-farzmcollective2025.git"
cd ada-2025-project-farzmcollective2025

# create conda environment
conda create -y -n FARZM python=3.13
conda activate FARZM


# install requirements
pip install -r pip_requirements.txt
```

## Abstract

The objective of this project is to investigate the calendar effects in the US stock market by testing their persistence, magnitude, and significance across different years, exchange sizes, and economic crises. We use historical daily data from the NASDAQ index from 1962 to April 2020. In this project, we focus on specific phenomena which include the Monday Effect, January Effect, Santa Claus Rally, Holiday Effect, and Sell in May Effect. Our motivation is to find out if these seasonal anomalies, which are often cited in financial literature and analysis, still hold power and presence in modern markets with the emergence of algorithm-based trading. We also want to find if there is a correlation between the interest rates, inflation rates, and these anomalies. By analyzing changes across different crises, we will tell a story about the evolution of market efficiency, ultimately assessing the practical utility of these effects for contemporary trading strategies.

## Research Questions

1. Are calendar effects actually real?
2. How do they evolve throughout the years?
3. How persistent is the calendar effect across different stock exchanges?
4. Does global crises like (Dot Com Bubble Burst,The Financial Crisis) make the calendar effects less significant?


## Additional Datasets

- Federal Funds Effective Rate
- 

We are considering to use these two additional datasets which represent FED interest rate and inflation rate in USA. We will consider also analyze whether there is any effect of inflation and interest rates over the calendar effect.

## Methods
We store the NASDAQ dataset in **Parquet** format rather than CSV because Parquet is designed for efficient handling of large-scale data. Unlike CSV files, which are plain text and must be fully read each time, Parquet is a **column-oriented, compressed, and binary** format. This makes it much faster to load, query, and filter specific variables—especially in a dataset with millions of rows and many columns like ours. 
### The Proposed Calendar Effects

We want to analyze these special cases of the calendar effect:

- Monday effect
- January effect
- Santa Claus Rally effect
- Turn-of-the-Month effect
- Half-Month effect
- Halloween effect (Sell in May and Go Away)
- Holiday effect

First we calculate the daily return, volatility and trade volume for all stocks. We also add a column with the logarithmic scale of the returns.

### Main Analysis

#### Calendar effects throughout the years.

- We try to find if there are any significant changes across different decades and if we can still depend on it now and how popular it was at the beginning 1960s vs now.

- We also want to check if the calendar effect was still persistent among different global crises (e.g.: Black Monday Crash, Dot Com Bubble Burst,The Financial Crisis, and COVID-19)


#### Calendar effect across different stock exchange:

We have 5 different stock exchanges:

- Q: NASDAQ Global (Large)
- N: NYSE (Large)
- A: NYSE American (Small)
- P: NYSE Arca
- Z: BATS

We can use these five stock exchanges to determine the different sizes of all the companies and accordingly we can check if the calendar effects differ based on the company size and capital.

### Results significance:

To examine the significance of the calendar effects in volatility and trading volume across different time scales (within a week, within a month, or within a year), we can perform statistical hypothesis tests based on p-values.
Specifically, the detectives rely on three complementary approaches to determine whether a calendar effect is statistically meaningful. First, **Welch’s Test** evaluates whether the average returns of a given calendar period (such as Mondays or January) differ significantly from the rest of the sample, while allowing for unequal variances between groups. Second, because market returns often deviate from normality, the **Mann–Whitney U Test** provides a distribution-free alternative that compares the entire ranking of returns rather than their averages, helping to detect systematic shifts not driven by a few large outliers. Finally, **regression analysis** allows the detectives to isolate calendar-based patterns while controlling for broader market dynamics such as volume, volatility, or macroeconomic conditions.


### Results:

We compare the results of different calendar effects to determine whether it makes sense or not and if we can use these effects to our benefit by establishing a portfolio strategy.

## Proposed timeline:

- Week 1-2 (11-05 - 11-19): In-depth data analysis of the different effects to answer our first research question based on the return, volume and also analysze the volatility
- Week 3 (11-20 - 11-26): Analysis of the evolution of the different effects over time
- Week 4 (11-27 - 12-03): measurement of the impact of these effects across different exchanges
- Week 5-6 (12-04 - 12-16): Try to find a way to take advantage of the calendar effect.

## Organization within the team:

### First milestone: individual analyses

Each person focuses on one or two special cases of the calendar effect:

- Aitor works on day of the week effects like Monday effect.
- Rana on month of the year effect like January effect and Santa Claus effect.
- Furkan on Halloween effect (Sell in May and Go Away).
- Zouhair on Half-Month effect Turn of the month.
- Melvyn on Holiday effect.

### Second milestone: merge the analyses

During this phase, the team unify the subprojects results, compare, identify overlapping patterns.

### Final milestone

The final results of analyses will allow us to determine whether the studied calendar effects are actually true or not and how can we benefit from them if they were actually true and significant.

<!-- ### How to use the library

Tell us how the code is arranged, any explanations goes here. -->

## Project Structure

The directory structure of the project looks like this:

```
├── data                        <- Project data files
│
├── src
│   ├── data
│   └── scripts
│
│
├── results.ipynb               <- a well-structured notebook showing the results
│
├── .gitignore                  <- List of files ignored by git
├── pip_requirements.txt        <- File for installing python dependencies
└── README.md
```
