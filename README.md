# MLB Player Injury Impact on Performance

## Project Outline
### Project Overview
We will be analyzing the injury data of MLB players from 2010 - 2021 and how these injuries impacted the production of players once they returned to the field. For this project, we will only be analyzing the impact of injuries that resulted in a player being placed on the MLB Injured List (formerly known as the Disabled List prior to the 2019 season). We will analyze the production of the players pre and post injury by comparing their WAR statistic. 

Injury Data Source: https://www.prosportstransactions.com/baseball/Search/SearchResults.php?Player=&Team=&BeginDate=2010-03-30&EndDate=2021-09-30&DLChkBx=yes&submit=Search&start=0"    
WAR Data Source: 

### Project Purpose
The goal behind this analysis is first to determine if there is any noticeable difference in player production before and after an injury. Although we understand it is certainly more nuanced than expecting to see consistent change due to any injury, we wanted to start simple. 

The hope is our first model simply analyzing time missed due to injury and a player's WAR value before and after that injury will provide us with some context that would be worth exploring deeper. For example, we would like to categorize different types of injuries on different types of players to observe if there are specific injuries you can expect to impact players in a consistent way. 

Whether or not we identify any trends, we expect these results to be useful in a variety of ways between interested parties. The impact on a small scale could help fantasy team managers or aspiring sports gamblers have a higher degree of confidence in their decision making process. The impact on a larger scale could shed light on best business practices for organizations following an injury to one of their rostered players, or perhaps suggest which teams in MLB have optimal injury recovery programs or staff in place. 

### Project Procedures
Using the source listed above, we scraped the data of all injury-related transactions in Major League Baseball from March 30th, 2010 to September 30th, 2021. These dates were arbitrarily chosen as the rough start of the 2020 season and the rough finish to the 2021 season. We chose 2010 as the start date because we wanted our data to be as free as possible from the influence of the steroid era on MLB. That said, we understand that pulling data as recent as the entire 2021 season will undoubtedly show influence from the COVID-19 pandemic which directly impacted the 2020 and 2021 seasons. We are aware of this concern and are prepared to remove the data from those two seasons if it appears they skew the data in a different direction than non-illness injuries. 

After retrieving all injury transaction data from those seasons, we cleaned the data, focusing on aligning player information with our WAR dataset, and calculating the total amount of days a player was on the Injured List due to their injury. We also separated specific information about the injuries in case we have time to further our analysis by categorizing types of injuries. In our WAR dataset, we also cleaned up the data to separate batting and pitching statitics and created a system of uniquely identifying players to prepare this dataset to be merged with our injury dataset. 

As the datasets were being prepared, we created a sample machine learning model using very small portions of the data just to ensure we prepared a model that would be capable of interpreting the data we intend to input. Additionally, we have created a database in PostgresSQL to merge our datasets and will host a live database on Amazon Web Services. 


## Communication Protocols
We used Slack as our main method of communication between group members outside of normal class hours. During class hours, we meet, discuss, and work on our project over Zoom video conferences. Additionally, we have been using a github repository to conglomerate all of our datasets and code. 

Each week, we have established tasks for each group member to carry out for the duration of the week. We have been sharing our updates via Slack, as well as any new or revised datasets. 