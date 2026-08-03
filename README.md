# Superstore Performance Dashboard — Profit Diagnostic in Power BI

**A profit diagnostic disguised as a sales dashboard.** Four years of Superstore transactions, rebuilt around one question a lot of retail dashboards never actually ask: is the business making money, or just moving product?

---

## The Problem

A retail business can look healthy on revenue alone while quietly losing money in specific product lines. Most dashboards default to Sales as the headline number because it is the bigger, more flattering figure. This project starts from a different premise: **Sales tells you activity. Profit tells you health.**

The brief I set for myself was a business case, not a charting exercise:

> Where is the business winning and losing money, and what should we do about it?

That single question, not a list of chart types, is what determined every KPI, every filter, and every color choice in this dashboard.

---

## What I Found

- **$286K in profit on $2M in sales**, a 12.5% margin, trending down year-over-year, a warning sign hiding underneath healthy-looking revenue growth.
- **One sub-category, Tables, is responsible for an $18K loss** on its own, driven by an average discount of roughly 25%. Two more, Bookcases and Supplies, are also net-negative.
- **The losses are self-inflicted, not demand-driven.** Copiers, Phones, and Chairs stay strongly profitable at discounts under 20%, which isolates the real problem: pricing discipline, not customer interest.
- **Profit is geographically lopsided.** West and East together generate close to 80% of total profit. Central and South are structurally underperforming.

I did not stop at finding these. I sized the fix: capping discounts on the three loss-making sub-categories recovers an estimated **$20K+ in margin without cutting a single sale.**

---

## How I Got There

**1. Framed it as a business case first.** Before opening Power BI, I wrote out the three questions a decision-maker actually needs answered: who drives profit, is growth real or just top-line, and what should change. Every visual on the dashboard maps back to one of these.

**2. Built the data model properly, not just the visuals.** A dedicated Date table, bounded to the dataset's actual four-year range and marked as an official date dimension, is what makes every year-over-year comparison on this dashboard reliable rather than approximate.

**3. Made profit the hero metric, deliberately.** Total Profit leads the KPI row, not Total Sales, the more common default. That one decision forces the dashboard to tell the true story from the first card a viewer sees, instead of burying it three clicks deep.

**4. Chose clarity over completeness.** An early version of the discount-versus-profit scatter chart plotted all 17 sub-categories and the insight disappeared into noise. I filtered it down to six, the three clearest winners against the three clearest losers, so the relationship between discounting and margin loss is visible without a caption.

**5. Caught and fixed a data-integrity issue before it shipped.** The trend chart initially sorted month-year labels alphabetically instead of chronologically, which distorted the entire line into a false, steadily declining trend. I traced it to the sort field, rebuilt it against a numeric Year-Month key, and the real, seasonal pattern in the business appeared.

---

## Recommendations Delivered

1. Cap discounts on Tables, Bookcases, and Supplies to recover $20K+ in margin without reducing sales volume.
2. Investigate why Central and South underperform West and East, whether the driver is pricing, product mix, or genuine regional demand.
3. Reallocate marketing and inventory investment toward Copiers, Phones, and Chairs, the strongest profit generators at the lowest discount levels.
4. Set a 15% maximum discount threshold on loss-prone sub-categories and monitor margin against it monthly.

---

## Dashboard Structure

**Page 1, Superstore Performance Overview**
KPI row (Profit, Sales, Margin, Orders, each with a live year-over-year indicator), a dual-axis Sales-vs-Profit trend line, and a sub-category profit ranking, color-coded so loss-makers are impossible to miss.

**Page 2, Regional & Category Dashboard**
The discount-versus-profit scatter chart, a regional profit treemap, and a plain-language Key Insights and Recommendation panel written for a business audience, not a technical one.

---

## Tools

Power BI Desktop (data modeling, DAX, dashboard design), Power Query (data shaping, date dimension), Canva (visual shell layered underneath live Power BI visuals).

---

## Skills Demonstrated

Business problem framing · Data modeling and DAX · KPI design · Root-cause analysis · Data visualization best practices · Debugging data integrity issues · Translating findings into stakeholder-ready recommendations

---

## Repository Contents

```
├── Sample - Superstore.pbix                  Power BI dashboard file
├── Sample - Superstore.csv                   Source dataset
├── Superstore_Dashboard_Presentation.pptx    Project presentation deck
├── /screenshots
│   ├── Superstore_Performance_Overview.png
│   └── Regional_Category_Dashboard.png
└── README.md                                 This file
```

---

## Data Source

Sample Superstore dataset, a widely used public retail dataset for business intelligence practice.

---

## Author

**Timothy Kehinde**
Data Analyst Intern, AnalystLab Africa

[LinkedIn](https://linkedin.com) · [GitHub](https://github.com) · [Portfolio](https://bit.ly/4qIn19W)
