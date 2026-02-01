#  IPL Analysis Dashboard (2008–2025)

## 📌 Project Overview
The **IPL Analysis Dashboard (2008–2025)** is a comprehensive and interactive **Power BI dashboard** designed to analyze Indian Premier League data across multiple seasons.  
It enables users to explore **team performance, player achievements, match statistics, and tournament trends** using KPI-driven visuals and dynamic filtering.

This project is built to demonstrate **real-world data analytics skills** and is suitable for **data analyst portfolios, academic projects, and recruiter evaluations**.

---

##  Tech Stack
- **Power BI Desktop** – Primary platform for dashboard development  
- **Power Query** – Data cleaning, transformation, and preprocessing  
- **DAX (Data Analysis Expressions)** – Advanced calculations and KPI measures  
- **Data Modeling** – Relationships across match, player, team, and season tables  
- **File Formats**
  - `.pbit` – Power BI template file  
  - `.png` – Dashboard preview images  

---

## 📂 Data Source
**Source:** Public IPL datasets (match-level & ball-by-ball data)

**Data Includes:**
- Match details (season, venue, teams, results)
- Ball-by-ball records (runs, wickets, extras)
- Player information
- Team and points table data

The dataset follows a **fact–dimension model** to ensure efficient filtering, aggregation, and performance.

---

## ✨ Features & Highlights

###  Business Problem
IPL generates massive volumes of data every season, but raw datasets are difficult to interpret without structured visualization.  
Stakeholders often lack a **single analytical view** to evaluate season outcomes, team consistency, and player dominance.

###  Goal of the Dashboard
To deliver a **season-wise analytical view** of IPL data that answers key performance questions through interactive visuals and KPIs.

###  Key Questions Answered
- Who won the IPL in a selected season and who was the runner-up?
- How many matches, teams, and venues were involved?
- Who won the Orange Cap and Purple Cap?
- Which players hit the most 4s and 6s?
- How did teams perform in the points table?

---

##  Key Visual Walkthrough

**🏆 Champions & Runner-Up Cards**  
Displays tournament winners and finalists dynamically based on the selected season.

**📈 KPI Summary Cards**  
Total Matches, Teams, Venues, 4s, 6s, Half-Centuries, and Centuries for a quick season snapshot.

**🧢 Orange Cap & Purple Cap Analysis**  
Highlights the top run scorer and wicket taker along with their teams and season performance.

**💥 Boundary Dominance**  
Identifies players with the most 4s and 6s in a season.

**📋 Points Table**  
Interactive table showing matches played, wins, losses, NR, ties, and total points.

---

##  Key DAX Measures Used

**Total Matches**
```DAX
Total Matches =
DISTINCTCOUNT(SeasonDataOnly[match_id])
```

**Total Sixes**
```DAX
Total Sixes =
CALCULATE(
    COUNTROWS(ball_by_ball_data),
    ball_by_ball_data[batsman_runs] = 6
)
```

**Total Fours**
```DAX
Total Fours =
CALCULATE(
    COUNTROWS(ball_by_ball_data),
    ball_by_ball_data[batsman_runs] = 4
)
```

**Orange Cap Runs**
```DAX
Orange Cap Runs =
CALCULATE(
    SUM(ball_by_ball_data[batsman_runs]),
    FILTER(
        ball_by_ball_data,
        ball_by_ball_data[batter] = SELECTEDVALUE(TopScorer[batter])
    )
)
```

**Purple Cap Wickets**
```DAX
Purple Cap Wickets =
CALCULATE(
    COUNT(ball_by_ball_data[isWicketDelivery]),
    ball_by_ball_data[isWicketDelivery] = 1
)
```

## Business Impact & Insights

Performance Evaluation: Identifies champions, top players, and consistent teams

Trend Analysis: Reveals scoring and bowling dominance across seasons

Decision Support: Useful for sports analytics case studies

Portfolio Value: Demonstrates Power BI, DAX, and data modeling expertise


##  Dashboard Preview

![IPL Analysis Dashboard](https://raw.githubusercontent.com/shravan1830/IPL-Analysis-Dashboard/main/IPL%20Analysis%20Dashboard%20Screenshot.png)

*Note: The screenshot above represents the main overview page of the IPL Analysis Power BI dashboard.*


## Future Enhancements

Player vs Team head-to-head analysis

Toss impact and venue-based insights

Match-level drill-through pages

## Author

Designed & Developed by Shravan Kalzunkar

🔗 GitHub Repository: https://github.com/shravan1830/IPL-Analysis-Dashboard

⭐ If you found this project insightful, feel free to star the repository!






