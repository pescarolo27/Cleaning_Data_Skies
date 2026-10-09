# Cleaning Data & the Skies

**Background:** Your are a data analyst working at an environmental company. You are tasked with evaluating ozone pollution across various regions.  
You've obtained data from the U.S. Environmental Protection Agency (EPA) containing daily ozone measurements at monitoring stations across California. However, like many real-world datasets, it’s far from clean: there are missing values, inconsistent formats, potential duplicates, and outliers.  
Before meaningful insights can be provided, the data needs to be cleaned and validated. Only then can it be analyzed to uncover trends, identify high-risk regions, and assess where policy interventions are most urgently needed.

**The Data:** The data is a modified dataset from the U.S. Environmental Protection Agency. The data file contains daily air quality summary statistics monitored for the state of California for 2024. Each row contains the date and the air quality metrics per collection method and site.

This project was done in September, 2025. It was part of a competition on _DataCamp_.  
Note that two files were completed & included in this repository: _Cleaning Data & the Skies I_, _Cleaning Data & the Skies II_. The only difference is in the last section (**Analysis IV**). Particularly, the latter file re-examined the data using hypothesis testing. Both files included analyses concerning the first objective, which had to do with preprocessing the data, because the subsequent analyses utilized the clean version of the dataset. In short, the first file (Part I) contains analyses for all four objectives, whereas the second file (Part II) contains a different analysis for the last objective plus the same analysis of the first objective.
- Due to the file size of the _Cleaning Data & the Skies I_ .ipynb file (~ 59 MB), it could not be uploaded to Github.

--------------------------------------------------------------------------------------------------------------------------------------------------------

### Brief Summary
This project analyzed environmental data pertaining to the state of California during 2024. More specifically, the air quality was evaluated across a variety of factors to assess how it evolved over the year & across different parts of the state, what areas saw particularly high concentrations of ozone, how air quality readings differed based on the collection method utilized, & how it may have been impacted according to the day of the week. Various tools & techniques were used to help evaluate such trends & risk levels including data visualizations, statistical analyses, aggregate analyses, & hypothesis testing.

There were four main objectives & corresponding sections in this project (**Analysis III** was made up of two subsections). For more information regarding details of analyses & findings for each objective, they can be found at the end of each section.

#### Analysis I - Exploratory Data Analysis, Data Preprocessing
The dataset required an evaluation to determine what preprocessing steps, if any, were necessary to prepare & enhance the data for valid, effective analyses. **Analysis I** covers this along with some initial explorative analyses that helped gain an initial understanding of the data.

The dataset, which contained about 54,700 data points, had a few variables that needed cleaning up, particularly concerning inconsistent values, missing values, & duplicates. While most were straightforward to handle, the dates in which observations were recorded were the most challenging. More specifically, about 9,200 records had a recorded date of "/2024" which, given that all the data was recorded in 2024, were essentially missing values. Ultimately, a manual form of linear interpolation was used built & used to impute about 8,600 of these vague dates.  
Other missing values were either left alone because they weren't directly relevant in the analyses or they were dealt with selectively within certain sections of the project later.

Following the implementation of these preprocessing steps, the cleaned version of the dataset, defined as `clean_df`, had 54,027 total data points & 20 variables.


#### Analysis II - Daily Maximum Ozone Levels Over Time, By Location
The second section examined the data across counties to determine how ozone levels varied over time in California throughout 2024. There are 58 unique counties in California but only 48 of them were present in the dataset. A variety of figures, including geospatial heatmaps & choropleths, plus some arithmetic helped to uncover which counties & areas in California exhibited the most & least variance in ozone concentrations during 2024.

Across the entirety of California, it was found that ozone levels peaked in July at around 0.054 parts per million (ppm) & then bottomed out in December & January at just over 0.030 ppm.  
This trend is replicated in most of the Californian counties during 2024. Additionally, counties that saw higher maximum ozone levels typically exhibited greater variance in terms of their ozone levels. At the beginning of the year, differences between average ozone levels were fairly similar across the 48 counties; however, these differences continued to widen from around April through July when most counties' ozone levels peaked in 2024. From then on, counties' average ozone levels generally declined as did the differences between their respective average ozone levels.

Through the handful of visuals presented in **Analysis II**, it was found that average monthly ozone levels meaningfully differed across three general areas in California.  
To summarize, areas towards the southern & central parts of California exhibited more variance & greater average ozone levels compared to the rest of the state. On the other hand, counties directly along the western coast as well as parts of northern California exhibited the least variance & least severe ozone concentrations during 2024.

__Recommendations__: The areas that exhibit the most severe ozone concentrations warrant the most resources in terms of intervention to help protect against potential health hazards & dangers associated with high ozone levels. Individuals who spend greater amounts of time outside will have a higher risk of such afflictions given that they are breathing the outside air more. Intervention techniques may want to consider such a factor when performing decision-making & distributing resources. On another note, organizations that provide such aid should expect greater demand for resources in the late spring & early summer when ozone levels, at least in California, tend to peak.  
Other organizations & agencies that may be more involved & dedicated to fighting climate change should continue to follow the evolution of ozone levels so that if they continue to rise in the following years & approach or exceed the EPA's "safe" concentration level (~ 0.070 ppm), they can be prepared to warn populations & those affected of what to expect & the health risks they may face. Using & deriving insights from ozone readings will be valuable when informing local & state governments & other able bodies as to the findings of such analyses & what they could mean in terms of peoples' health & living conditions.


#### Analysis III
This section evaluated two inquiries separately. The first part analyzed areas of California with high ozone readings in 2024. The second investigated the different collection methods that were used to record ozone levels & their measurements.

#### Analysis III-A - High-Ozone Areas
Two primary metrics were used to evaluate areas of California that consistently showed high concentrations of ozone. Importantly, this analysis sought to identify areas in California that exhibited **both** consistency & high magnitudes of ozone levels. To determine which areas had higher ozone levels, averages were used, whereas for consistencies of ozone levels, variances were used.  
Counties were used to evaluate ozone levels on a geographical basis. Additionally, ozone levels of the counties were analyzed on a monthly basis to evaluate consistency & how much they evolved.

There were ten counties that best characterized areas with high-but-consistent levels of ozone: Amador, Butte, El Dorado, Inyo, Mariposa, Nevada, Shasta, Sutter, Tuolumne, & Ventura.
- Overall, the Mariposa, Inyo, El Dorado, Ventura, Tuolumne counties exhibited ozone levels in 2024 that were the most severe & the most consistent.

The EPA considers ozone levels of 0.070 ppm or higher to be unhealthy & potentially dangerous. The average monthly ozone levels of these ten most relevant counties peaked at about 0.060 ppm in July, so these areas did not pose imminent danger in 2024; however, with increasing levels of climate change & warming temperatures, this could change soon.

__Recommendations__: The areas identified in this section are among those with the greatest risk of suffering health problems from high ozone levels. As such, the relevant populations will likely require considerable assistance in mitigating such risks particularly in the late spring & early summer when ozone levels are likely to peak.

#### Analysis III-B - Ozone Levels by Collection Method
In the dataset, there are four defined collection methods which are named using numerical codes; however, there were about 6,300 data points whose collection method was missing. Instead of ignoring or removing them from this section, they were compiled into a single group with a "Missing" method code. So, five groups were analyzed in total.  
Two general analyses were performed that involved evaluating the distributions & averages of ozone levels across these five method groups across both 2024 as a whole & on a monthly basis.

In short, these analyses revealed that the "53" collection method saw higher ozone levels that were noticeably greater than the other methods. Conversely, the "47" method, along with observations with a "Missing" method, saw slightly smaller ozone levels than the others.  
Generally, the average monthly ozone levels were similar in months that saw smaller abundances of ozone across the different methods; however, as these levels increased in the middle of the year, the methods' observations become more inconsistent with one another. The "47" & "Missing" methods recorded ozone levels that bucked part of the general trend observed throughout California, specifically from April through June & August through October.

__Recommendations__: Given that differences in ozone levels were more significant when ozone levels peaked, this could indicate a potential underlying bias in the methods. For example, perhaps certain collection methods resided in areas where ozone levels were naturally higher than others at certain points in the year. Alternatively, if the methods differed due to technological reasons, maybe some technologies faltered more than others when ozone levels become more severe.  
To truly get an understanding as to what meaningful patterns & relationships might exist in the data across the collection methods, they would need to be examined further & additional context would need to be obtained about them.


#### Analysis IV - Day of Week & Ozone Levels
It was theorized that ozone levels may differ between weekdays & weekends because different kinds & quantities of urban activity usually take place during the week & on the weekend. For example, a large chunk of the general population has to commute to & from their workplace between Monday & Friday, whereas they are more likely to stay home on the weekend. Through the usage of transportation, gas & diesel vehicles emit chemicals & gases that can form into ozone in certain conditions, specifically when interacting with sunlight & high temperatures. This reasoning is behind the inquiry as to whether urban activity might relate to ozone levels.

In the first file (_Cleaning Data & the Skies I_), straightforward statistical analyses were conducted the results of which proved inconclusive. More specifically, ozone levels were analyzed across weekdays vs weekends, different days of the week, on a monthly basis, & across a specific county. Ultimately, they failed to find any meaningful differences in the ozone levels.  
The second file (_Cleaning Data & the Skies II_) extended these analyses into more powerful statistical techniques, specifically hypothesis tests.

Given the nature of the data, parametric, two-tailed t-tests were used to evaluate whether average ozone levels were different between weekdays & weekends in California in 2024. First, these averages were assessed across the entire dataset. Using a significance level of five percent, the hypothesis test yielded a p-value of about 0.26%. As such, the null hypothesis was rejected in favor of the alternative. More specifically, the average ozone level observed during the week was about 0.00043 ppm higher than on the weekends. The p-value indicates that this difference is statistically significant.

Secondly, average ozone levels across weekdays & weekends were evaluated specifically for the county of Los Angeles. Using a significance level of five percent, the hypothesis test yielded a p-value of about 4.06%. As such, the null hypothesis was rejected in favor of the alternative. More specifically, the average ozone level observed on the weekends in Los Angeles county was about 0.001143 ppm higher than during the week. The p-value indicates that this difference is statistically significant.

__Recommendations__: If it is assumed that urban activity is the main catalyst regarding differences in ozone levels between weekends & weekdays in this dataset, then these results indicate that urban activity did have a meaningful effect on ozone levels observed in California in 2024 across different days of the week. With this in mind, urban activity generally resulted in ozone levels being slightly higher during the week than on weekends during 2024 in California. Conversely, for the county of Los Angeles, urban activity resulted in ozone levels being slightly lower during the week than on weekends during 2024.

These findings could be used in a variety of ways depending on how urban activity is defined & interpreted. For instance, these findings could indicate that vehicular usage was slightly more common during the week across California in 2024, whereas for Los Angeles county, it was slightly more common on the weekends. Such insights could be used when assessing traffic patterns & associated problems such as congestion, traffic jams, potential for vehicular accidents, & delays from construction projects. As an example, it might affect less people in Los Angeles county to do more construction on roadways on weekdays than on weekends. Alternatively, emergency services could implement these findings to help prepare for certain days & times in which accidents may be more likely to happen as a result of increased urban activity.

Further analyses could continue to drill down into these variables & others in the dataset such as the time of year (i.e. month, season), additional counties, & the collection method. Such analyses could provide insights as to how meaningful changes in average ozone levels on weekends & weekdays were over time, whether ozone levels significantly differed by county, & whether the data recorded by different collection methods were meaningfully different across weekends & weekdays.
