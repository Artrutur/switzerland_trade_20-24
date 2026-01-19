# 1. Data Source and Definitions

## Data Source

UN Comtrade Database (https://comtradeplus.un.org/) is a rich source of information about world trade.
There is data regarding chosen countries, trade flows, modes of transport and types of commodities during a selected period of time.

On the website, after creating an account, it is possible to download CSV files up to 100'000 records by choosing specific conditions of searching.
![Comtrade_screen](02_jpg/Comtrade_screen.JPG)


## Definitions

I was interested in finding data about **Switzerland's trading partners** over the last 5 available years: **2020-2024**.

Then, I limited the outcomes to the **lowest level of aggregation of commodities (HS-2)**, which means wider and less detailed groups of products, but still detailed enough to draw specific insights.

**HS**, which stands for **Harmonized System**, are codes commonly used throughout the import and export process for the classification of goods (https://www.trade.gov/harmonized-system-hs-codes)

To clarify, this can be explained by an example:

`HS-2` code no. 52: "Cotton"

`HS-4` code no. 5204: "Cotton sewing thread, whether or not put up for retail sale"

`HS-6` code no. 520411: "Cotton; sewing thread, containing 85% or more by weight of cotton, not put up for retail sale"

In order to understand **physical flows**, I also wanted to see **modes of transport** by which commodities arrive in and are sent from Switzerland.

# 2. First Questions and Ideas about Structuring the Data

## Questions
First questions that popped out of my head while thinking about that dataset were:

**What Swiss Economy consist of?**

**What are the types of most imported and exported goods?**

**With whom does Switzerland trade the most?**

**What transportation channels are the most popular?**

**How has it changed over the last 5 years?**

## Structure
The tables come with many columns, which brings a lot of information, but also causes some **errors**.

One of the problems was **special characters** in the names of the countries and in commodities' explanations or in their units.

To simplify the process of getting this information, I decided to create **2 dimension tables** (name of `countries` and name of `commodities` with their codes) and **1 fact table** (with the numbers for all the partners throughout 5 years).

It was possible to download the dimension tables separately, although they needed cleaning.

To create 1 fact table, I needed to download data for each year separately (as shown on the print-screen above), while it was the biggest chunk of data (ca. 60'000+ rows) which fitted in the limits. After that, all 5 tables could have been combined as they contained the same fields.


# 3. Data Cleaning and Structuring (SQL)

## Fact Table
Because of the limited `encoding` options in DataLab, I first uploaded and reduced the tables by unnecessary columns in **BigQuery** for each **Fact Table** (each year) : `ch_2020`,`ch_2021`,`ch_2022`,`ch_2023`,`ch_2024`.

This allowed to get rid of problematic characters and simplify the tables.

One of the tables had a problem with a **CSV export**, as `nulls` were not correctly read.

A way out was to export the same table to **XLSX** format from the primary source (UN Comtrade), open it in Excel and then export it as CSV.

![Export_error](Export_error.jpg)


## **Appendix**

It seems that biggest 'deficit-makers' are countries who sell precious metals and stones to Switzerland. As my level of detail is limited here, at this point I need to go deeper and download dataset which has more detail information regarding commodities_code = 71, which is also a group of goods with the biggest trading value.

For that I needed to download next 2 tables (because of website limits) with HS-4 numbers 7101-7118, and combine them:

![Comtrade_code_71_a](Comtrade_code_71_a.JPG)
![Comtrade_code_71_b](Comtrade_code_71_b.JPG)

While HS-4 codes were still vague, and as one of them appeared the most of the time, I decided to go one step further.
HS-4 code 7108 represents gold in general. I wanted to dig deeper and break down trades regarding gold with HS-6 codes:
![Comtrade_code_7108](Comtrade_code_7108.JPG)
