# Stories-Analysis-EECE-490
Analysis of Stories Coffee sales data from 25 branches to uncover trends, insights, and patterns. Includes data cleaning, exploratory analysis, modeling, and visualizations for business decision support.



CLASSIFICATION IDEA:

Instead of relying on intuition, we built a simple and explainable framework using two normalized indices:

R (Relative Demand Index) → measures item popularity
M (Relative Margin Index) → measures item profitability

Together, they classify products into actionable categories: promote, avoid discounting, improve visibility, or remove.

Methodology

Retail performance depends on two factors:

Demand (popularity)

Profit efficiency (margin)

Because branches differ in size, we normalize all metrics to remove scale bias and allow fair comparison.

Relative Demand Index (R)

Share(i,b) = Revenue(i,b) / TotalRevenue(b)
MedianShare(i) = median over branches of Share(i,b)
R(i,b) = Share(i,b) / MedianShare(i)

R > 1 → More popular than typical
R < 1 → Underperforming

Relative Margin Index (M)

Margin(i,b) = Profit(i,b) / Revenue(i,b)
MedianMargin(i) = median over branches of Margin(i,b)
M(i,b) = Margin(i,b) / MedianMargin(i)

M > 1 → Higher margin than typical
M < 1 → Lower margin than peers

We use the median (not the mean) because retail data contains outliers. The median provides a more stable and robust benchmark.

Decision Matrix

R > 1 and M > 1 → Popular and profitable → Promote or possibly raise price
R < 1 and M > 1 → Profitable but weak demand → Promote or improve visibility
R > 1 and M < 1 → Popular but low margin → Avoid discounting or review pricing
R < 1 and M < 1 → Weak and low profit → Consider removing

By separating popularity (R) from profitability (M), the system avoids common retail mistakes such as discounting already popular low-margin items or ignoring high-margin items with low visibility. The result is a simple, explainable, and data-driven product optimization engine.
