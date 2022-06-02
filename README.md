# Predicting Major League Baseball Player Performance
### Using player WAR information and injury data to anticipate performance growth or contraction

WAR (Wins Above Replacement) is an attempt to summarize a player's total contributions to their team into one statistical number. Using varying mathematical formats, a WAR number asks the question - "If a player was injured at the team needed a replacement, how much value would the team be losing (or gaining)?)" 

A standard WAR hovers around a +2, meaning that if a player with a higher number was injured, a team would be losing experience by bringing up a replacement, while anything less that 2 or negative numbers would be a gain in performance for a team.

Though not without controversy, WAR numbers are fairly reliable to rate a player's individual performance year-to-year. 

## Selecting the Topic
We selected the topic based on a shared interest in baseball, statistics, and the availability of data. Our team felt that building a prediction model to estimate the total effects an injury may have on a player's WAR number would be beneficial to in both a healthcare sense (does modern healthcare impact recovery time), as well as an information source for fantasy or sports betting.


## Looking at the Data
Our primary sources of data were Baseball-Reference and aggregated WAR data from FanGraphs and Baseball-Reference, compiled by Neil Paine.

Both sources were chosen by the completeness of data, both in terms of years and players available, as well as accuracy with limited missing data.

Our data sources were fairly consistent between both sources; however, we did focus on aligning player information using player name, team, and year. Through the process, we did experience a small loss of data, around 1.5%, however our group determined that was an acceptable loss, since our data included over 18,000 data rows.

Our team limited our data range to 2010, or 14 years. We felt that there was a possibility of skewed data prior to that time, due to the ongoing steroid scandals of the 1990s and early 2000s. There's also ongoing controversy with WAR numbers favoring players in earlier years due to the variance in skill levels. Injury data before the 1990s is also far from complete.


## Questions Overview
- Can we predict a player's WAR number following an injury?
- Could we accurately predict a player's recovery time based on injury?
- Is there a direct correlation between time on the injured list and decrease in WAR?
- Does WAR ever bounce back to pre-injury levels and how quickly?


## Results


## Future Analysis Possibilities


Content 
The presentation tells a cohesive story about their project, including the 
following:
✓ Selected topic
✓ Reason why they selected their topic
✓ Description of their source of data
✓ Questions they hope to answer with the data
✓ Description of the data exploration phase of the project
✓ Description of the analysis phase of the project
✓ Technologies, languages, tools, and algorithms used throughout the project 
✓ Result of analysis
✓ Recommendation for future analysis
✓ Anything the team would have done differently 






# MLB Player Injury Impact on Performance

## Project Outline
### Project Overview
We will be analyzing the injury data of MLB players from 2010 - 2021 and how these injuries impacted the production of players once they returned to the field. For this project, we will only be analyzing the impact of injuries that resulted in a player being placed on the MLB Injured List (formerly known as the Disabled List prior to the 2019 season). We will analyze the production of the players pre and post injury by comparing their WAR statistic. 

Injury Data Source: https://www.prosportstransactions.com/baseball/Search/SearchResults.php?Player=&Team=&BeginDate=2010-03-30&EndDate=2021-09-30&DLChkBx=yes&submit=Search&start=0"    
WAR Data Source: 

### Project Purpose
The goal behind this analysis is first to determine if there is any noticeable difference in player production before and after an injury. Although we understand it is certainly more nuanced than expecting to see consistent change due to any injury, we wanted to start simple. 

The hope is our first model simply analyzing time missed due to injury and a player's WAR value before and after that injury will provide us with some context that would be worth exploring deeper. For example, we would like to categorize different types of injuries on different types of players to observe if there are specific injuries you can expect to impact players in a consistent way. 

Whether or not we identify any trends, we expect these results to be useful in a variety of ways between interested parties. The impact on a small scale could help fantasy team managers or aspiring sports gamblers have a higher degree of confidence in their decision-making process. The impact on a larger scale could shed light on best business practices for organizations following an injury to one of their rostered players, or perhaps suggest which teams in MLB have optimal injury recovery programs or staff in place. 

### Project Procedures
Using the source listed above, we scraped the data of all injury-related transactions in Major League Baseball from March 30th, 2010 to September 30th, 2021. These dates were arbitrarily chosen as the rough start of the 2020 season and the rough finish to the 2021 season. We chose 2010 as the start date because we wanted our data to be as free as possible from the influence of the steroid era on MLB. That said, we understand that pulling data as recent as the entire 2021 season will undoubtedly show influence from the COVID-19 pandemic which directly impacted the 2020 and 2021 seasons. We are aware of this concern and are prepared to remove the data from those two seasons if it appears they skew the data in a different direction than non-illness injuries. 

After retrieving all injury transaction data from those seasons, we cleaned the data, focusing on aligning player information with our WAR dataset, and calculating the total amount of days a player was on the Injured List due to their injury. We also separated specific information about the injuries in case we have time to further our analysis by categorizing types of injuries. In our WAR dataset, we also cleaned up the data to separate batting and pitching statistics and created a system of uniquely identifying players to prepare this dataset to be merged with our injury dataset. 

As the datasets were being prepared, we created a sample machine learning model using very small portions of the data just to ensure we prepared a model that would be capable of interpreting the data we intend to input. Additionally, we have created a database in PostgresSQL to merge our datasets and will host a live database on Amazon Web Services. 


## Communication Protocols
We used Slack as our main method of communication between group members outside of normal class hours. During class hours, we meet, discuss, and work on our project over Zoom video conferences. Additionally, we have been using a github repository to conglomerate all of our datasets and code. 

Each week, we have established tasks for each group member to carry out for the duration of the week. We have been sharing our updates via Slack, as well as any new or revised datasets.
