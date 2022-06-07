# Predicting Major League Baseball Player Performance
### Using player WAR information and injury data to anticipate performance growth or contraction
https://carolinestyc.github.io/Baseball-WAR-Webpage/ · https://mdbinger.github.io/MLB_player_page/

## Project Members
[Brett Liddicoat](https://github.com/bmliddicoat) · [Michael Binger](https://github.com/mdbinger) · [Caroline Styc](https://github.com/carolinestyc) · [Brian Wheatley](https://github.com/brianrwheatley/)

WAR (Wins Above Replacement) is an attempt to summarize a player's total contributions to their team into one statistical number. Using varying mathematical formats, a WAR number asks the question - "If a player was injured and the team needed a replacement, how much value would the team be losing (or gaining)?)" 

A standard WAR hovers around a +2, meaning that if a player with a higher number was injured, a team would be losing experience by bringing up a replacement.  Theoretically, anything below 2 or a negative number would be a gain in performance for a team.

Though not without controversy, WAR numbers are fairly reliable to rate a player's individual performance year-to-year. 

## Selecting the Topic & Overview
We selected the topic based on a shared interest in baseball, statistics, and the availability of data. Our team felt that building a prediction model to estimate the total effects an injury may have on a player's WAR number would be beneficial to in both a healthcare sense (does modern healthcare impact recovery time), as well as an information source for fantasy or sports betting.

With our analysis of injury data of Major League Baseball players, our goal is to determine how the injuries impacted the production of players upon returning to the field.  Our analysis is limited to injuries that resulted in the player being placed on the MLB Injured List (formerly the Disabled List).  The analysis focuses on the performance of players pre- and post-injury by comparing WAR numbers. 

## Group Communications
Our group used Slack as our main form of communication outside of class hours, while during class, we met, discussed, and worked on our project over Zoom.

Each week, we reviewed progress, then divided tasks among ourselves to finish over the next week. We shared progress updates via Slack, as well as new or revised data.


## Looking at the Data
Our primary sources of data were Baseball-Reference and aggregated WAR data from FanGraphs and Baseball-Reference, compiled by [Neil Paine](https://github.com/NeilPaine538/MLB-WAR-data-historical). Our injury data was scraped from Pro Sports Transactions.

Both sources were chosen by the completeness of data, both in terms of years and players available, as well as accuracy with limited missing data.

Our data from each source was fairly consistent between both sources; however, we did focus on aligning player information using player name, team, and year. Through the process, we did experience a small loss of data, around 1.5%, however our group determined that was an acceptable loss, since our data included over 18,000 data rows.

Our team limited our data range to begin in 2010, or 12 years. We felt that there was a possibility of skewed data prior to that time, due to the steroid scandals of the 1990s and early 2000s. There's also ongoing controversy with WAR numbers favoring players in earlier years due to the variance in skill levels. Injury data before the 1990s is also far from complete.

Originally, we planned to host our data as PostgreSQL on AWS.  However, looking at our compiled data, we determined dropping our CSV files into an AWS S3 bucket was the better solution, both in terms of access and cost.

## Questions Overview
- Is there a direct correlation between time on the injured list and decrease in WAR?
- Does WAR ever bounce back to pre-injury levels and how quickly?

## Results
We created a sample machine learning model using very small portions of the data, to ensure we prepared a model that would be capable of interpreting the data we intend to input.

Once we cleaned and organized our data, we put aside our initial plan to run a linear regression model on our data. The classification wasn’t what we were after.

We settled on running our data through a neural network.  The model was used to create a prediction classification - if a player was above 2 WAR (everyday player) and WAR regression or progression from year-to-year. The results of the analysis show that an injured player showed a quicker decline in abilities (WAR) by age compared to non-injured players. For non-injured players, regression occurred after age 30. In contrast, injured players showed regression after age 24. This six-year difference shows that injuries cause a decline in player ability and value for a team, even in younger players.

Our model featured four to five hidden layers, using both the Relu and Sigmoid activations. Our model was then compiled using the Adam optimizer. We ran our data through two models – one for players with above average WAR, the other for WAR change from season to season. Through training with 100 epochs, we were able to attain a prediction accuracy of 84-86% for both models.

## Future Analysis Possibilities
Our analysis is limited to overall player injuries. We have discussed that future analysis could breakdown the injury data more – to include location of injury, type of injury, or recurring injury.  For example, a torn rotator cuff may be more detrimental to the WAR number for a pitcher, while knee injuries may be more impactful to a batter’s WAR.

By categorizing injuries and different player positions, we could possibly observe if there are specific injuries we’d expect to impact players in a consistent way.

Using our neural model, we could also further build on the analysis to predict a player's recovery time based on the type of injury, as well possibly predicting a player's WAR number following the injury.

Our modeling doesn’t fully consider a player’s team or the player’s salary when predicting WAR recovery. Further analysis may show correlation between how well a team is funded and recovery time after injury.
