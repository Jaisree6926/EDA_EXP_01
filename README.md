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

season_counts = matches['season'].value_counts().sort_index()
plt.figure(figsize=(8,4))
sns.barplot(x=season_counts.index, y=season_counts.values, palette="viridis")
plt.title("Number of Matches per Season")
plt.xlabel("Season")
plt.ylabel("Matches")
plt.show()

team_wins = matches['winner'].value_counts()
print("\nTop Winning Teams:\n", team_wins.head(5))
plt.figure(figsize=(8,4))
sns.barplot(x=team_wins.head(5).index, y=team_wins.head(5).values, palette="magma")
plt.title("Top 5 Winning Teams")
plt.xlabel("Team")
plt.ylabel("Wins")
plt.show()

toss_decision = matches['toss_decision'].value_counts()
print("\nToss Decisions:\n", toss_decision)
plt.figure(figsize=(6,4))
sns.barplot(x=toss_decision.index, y=toss_decision.values, palette="Set2")
plt.title("Toss Decisions (Bat or Field)")
plt.show()

venue_counts = matches['venue'].value_counts().head(5)
print("\nTop Venues:\n", venue_counts)
plt.figure(figsize=(8,4))
sns.barplot(y=venue_counts.index, x=venue_counts.values, palette="coolwarm")
plt.title("Top 5 Venues by Matches Hosted")
plt.xlabel("Matches Hosted")
plt.ylabel("Venue")
plt.show()

```
  **Output**
  
<img width="1455" height="800" alt="Screenshot 2026-02-02 085246" src="https://github.com/user-attachments/assets/b3e86731-f884-4e85-81c2-eb7462f6bec7" />

<img width="1804" height="761" alt="Screenshot 2026-02-02 085219" src="https://github.com/user-attachments/assets/9d83a0c0-3a4e-45ed-8624-cf182b17ec11" />

<img width="1819" height="786" alt="Screenshot 2026-02-02 085206" src="https://github.com/user-attachments/assets/540dbbd5-ffd3-4769-af71-722c0fb9e088" />

<img width="1775" height="270" alt="Screenshot 2026-02-02 085145" src="https://github.com/user-attachments/assets/d328d9fb-9408-479e-93f6-ad8146f3adb2" />

<img width="1638" height="774" alt="Screenshot 2026-02-02 085309" src="https://github.com/user-attachments/assets/9640187d-6455-4cf4-9838-c6d124fc282f" />

<img width="1405" height="698" alt="Screenshot 2026-02-02 085256" src="https://github.com/user-attachments/assets/3b72071d-4a0b-42bd-967e-22c61f633b9c" />

 ** Result**
  This experiment is executed successfully



Highlight the stadiums hosting maximum matches.
