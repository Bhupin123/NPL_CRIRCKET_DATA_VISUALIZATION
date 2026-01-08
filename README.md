# 🏏 NPL Cricket Match Data Analysis (EDA)

This project performs **Exploratory Data Analysis (EDA)** on a cricket match dataset using  **Python, Pandas, Matplotlib, and Seaborn**.  
The goal is to understand match outcomes, toss impact, team performance, venues, and player contributions using **simple and clear visualizations**.

---

## 📌 Project Objectives

- Analyze match results and team performance  
- Understand the impact of toss decisions  
- Identify popular cities and venues  
- Analyze win types and scoring patterns  
- Highlight top-performing players  

---

## 🛠️ Tech Stack

- Python  
- Pandas  
- Matplotlib  
- Seaborn  
- Jupyter Notebook  

---

## 📊 Exploratory Data Analysis (EDA)

Below is the **complete EDA code in a single section**:

```python
import pandas as pd
import matplotlib.pyplot as plt
import seaborn as sns

plt.style.use("default")

# 1. Matches won by each team
plt.figure(figsize=(10,5))
df['winner'].value_counts().plot(kind='bar')
plt.title("Total Matches Won by Each Team")
plt.xlabel("Team")
plt.ylabel("Number of Wins")
plt.show()

# 2. Toss winner vs match winner
toss_match_win = (df['toss_winner'] == df['winner'])
toss_match_win.value_counts().plot(kind='bar')
plt.title("Does Toss Winner Also Win the Match?")
plt.xticks([0, 1], ['Lost Match', 'Won Match'], rotation=0)
plt.ylabel("Number of Matches")
plt.show()

# 3. Toss decision preference
sns.countplot(x='toss_decision', data=df)
plt.title("Toss Decision Preference")
plt.xlabel("Decision")
plt.ylabel("Count")
plt.show()

# 4. Types of match wins
sns.countplot(x='win_type', data=df)
plt.title("Types of Match Wins")
plt.xlabel("Win Type")
plt.ylabel("Count")
plt.show()

# 5. Runs distribution by teams
sns.boxplot(data=df[['team_1_runs', 'team_2_runs']])
plt.title("Runs Distribution by Teams")
plt.xlabel("Team")
plt.ylabel("Runs")
plt.show()

# 6. Top 10 cities hosting matches
df['city'].value_counts().head(10).plot(kind='bar')
plt.title("Top 10 Cities by Number of Matches")
plt.xlabel("City")
plt.ylabel("Matches")
plt.show()

# 7. Top 10 players of the match
df['player_of_the_match'].value_counts().head(10).plot(kind='bar')
plt.title("Top 10 Player of the Match Winners")
plt.xlabel("Player")
plt.ylabel("Awards")
plt.show()

# 8. Super over analysis
sns.countplot(x='super_over', data=df)
plt.title("Super Over Matches")
plt.xlabel("Super Over")
plt.ylabel("Count")
plt.show()

