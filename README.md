# NAME: SUSINDHAR K M
# REGISTER NO:212223040218

**#Experiment 1: EDA in IPL Dataset**
**Aim:**
To perform Exploratory Data Analysis (EDA) on the IPL matches dataset and derive insights about matches per season, winning teams, toss decisions, and top venues.

**Algorithm / Procedure:**

**1.Import Libraries**
  Import pandas for data handling.
  Import matplotlib and seaborn for visualization.
**2.Load Dataset**
  Use pd.read_csv() to load the IPL matches dataset.
  Check dataset shape using .shape.
  View first 5 rows using .head().
**3.Matches per Season (Univariate Analysis)**
  Group data by season and count matches.
  Plot a bar chart to visualize growth/decline in matches.
**4.Top Winning Teams (Univariate Analysis)**
  Use value_counts() on the winner column.
  Plot top 5 winning teams in a bar chart.
**5.Toss Decisions (Univariate Analysis)**
  Count toss decision preferences (bat vs field).
  Plot results using a bar chart.
**6.Top Venues (Univariate Analysis)**
  Count matches per venue.
  Display top 5 venues with a horizontal bar chart.
**7.Draw Insights**
  Observe patterns in toss decisions.
  Identify teams with consistent winning trends.
  
  **Program**
```
import pandas as pd
import matplotlib.pyplot as plt
import seaborn as sns
matches = pd.read_csv("matches.csv")
print("Dataset Shape:", matches.shape)
print(matches.head()) 
```
<img width="833" height="458" alt="image" src="https://github.com/user-attachments/assets/d9afd31e-12d3-47b0-8851-272e23e074ce" />



```
season_counts = matches['season'].value_counts().sort_index()
print("\nMatches per season:\n", season_counts)
```
<img width="452" height="183" alt="image" src="https://github.com/user-attachments/assets/7777843b-b3ce-4f9c-92ae-1ab933dd76bf" />



```
plt.figure(figsize=(8,4)) 
sns.barplot(x=season_counts.index, y=season_counts.values, palette="viridis")
plt.title("Number of Matches per Season")
plt.xlabel("Season") 
plt.ylabel("Matches")
plt.show()
```
<img width="737" height="312" alt="image" src="https://github.com/user-attachments/assets/1fbc0df6-d94a-44b9-bc2b-77987cd77a03" />


```
toss_decision = matches['toss_decision'].value_counts()
print("\nToss Decisions:\n", toss_decision)
plt.figure(figsize=(6,4)) 
sns.barplot(x=toss_decision.index, y=toss_decision.values, palette="Set2") 
plt.title("Toss Decisions (Bat or Field)") 
plt.show()
```
<img width="627" height="369" alt="image" src="https://github.com/user-attachments/assets/52880d47-3c02-4397-9216-134711ca72cf" />


```
venue_counts = matches['venue'].value_counts().head(5) 
print("\nTop Venues:\n", venue_counts)
plt.figure(figsize=(8,4))
sns.barplot(y=venue_counts.index, x=venue_counts.values, palette="coolwarm")
plt.title("Top 5 Venues by Matches Hosted") 
plt.xlabel("Matches Hosted") 
plt.ylabel("Venue") 
plt.show()
```
<img width="821" height="425" alt="image" src="https://github.com/user-attachments/assets/8ed7ed0b-5770-447f-b9f7-5a6f080653fa" />


 # Result:
This experiment is executed successfully
